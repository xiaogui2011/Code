# 协程池

创建一个具有固定数量工作协程的工作池。这些工作协程可以并发地处理Foo操作

## 工作协程

```go
type Worker struct {
    ID          int
    TaskChannel chan func() // 用于接收任务的通道
    Quit        chan struct{} // 用于信号协程退出的通道
}
```

### 初始化

```go
func NewWorker(id int) *Worker {
    worker := &Worker{
        ID:          id,
        TaskChannel: make(chan func()),
        Quit:        make(chan struct{}),
    }

    go worker.Start()
    return worker
}
```

### 实现工作协程的 Start 方法：

```go
func (w *Worker) Start() {
    for {
        select {
        case task := <-w.TaskChannel:
            task() // 执行接收到的任务
        case <-w.Quit:
            return
        }
    }
}
```

## 协程池

```go
type Pool struct {
    Workers []*Worker
}
```

### 初始化协程池

```go
func NewPool(workerCount int) *Pool {
    pool := &Pool{}
    for i := 0; i < workerCount; i++ {
        pool.Workers = append(pool.Workers, NewWorker(i))
    }
    return pool
}
```

### 实现提交任务到池的方法：

```go
func (p *Pool) SubmitTask(task func()) {
    worker := p.selectWorker()
    worker.TaskChannel <- task
}
```

### 实现选择可用工作协程的方法：

```go
func (p *Pool) selectWorker() *Worker {
    // 为演示目的简单使用轮询选择工作协程
    return p.Workers[rand.Intn(len(p.Workers))]
}
```

### 在你的MongoDB操作中使用池

```go
// 使用特定数量的工作协程初始化池
pool := NewPool(5)

// 提交MongoDB操作到池的示例
pool.SubmitTask(func() {
    // 这里放入你的MongoDB操作代码
})
```
