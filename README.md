# hello-go-redis.go

My first program in go. An example of how to use go with redis.

## Usage

```bash
go run hello-go-redis.go
```

## Setup

### Install Go

Install Go. As of writing [this](https://go.googlecode.com/files/go1.1.2.darwin-amd64.pkg) was the latest version.

You can find the list of all available downloads by clicking from [the go download page](http://golang.org/doc/install).

### Install Mercurial

You must have Mercurial installed for the `go get` command to work. So let's install Mercurial.

Next, use go to get the gotour.

```bash
brew update   
brew doctor
brew install mercurial
```
### Setup GOPATH

Create your go workspace. This is just the way go works. Do the following.

```bash
mkdir gocode
```

Open up .bashrc (or .zshrc if using zsh).

```bash
vim .bashrc
```

On the last line set the GOPATH.

```bash
export GOPATH="$HOME/gocode"
```

### Create your project inside your workspace 

Now, we can create our project inside our gocode workspace.

```bash
cd gocode
mkdir -p src/github.com/username
```

### Create the hello-go-redis project

```bash
cd src/github/username
mkdir hello-go-redis
cd hello-go-redis
vim hello-go-redis.go
```

Paste the following into `hello-go-redis.go`.

```go
package main

import "fmt"
import "github.com/garyburd/redigo/redis"

func main() {
  fmt.Printf("hello, go\n")
  //INIT OMIT
  c, err := redis.Dial("tcp", ":6379")
  if err != nil {
    panic(err)
  }

  defer c.Close()

  //set
  c.Do("SET", "hello", "world")

  //get
  world, err := redis.String(c.Do("GET", "hello"))
  if err != nil {
    fmt.Println("key not found")
  }

  fmt.Println(world)
  //ENDINIT OMIT
}
```

Get redis.

```bash
go get github.com/garyburd/redigo/redis
```

### Run it

```bash
go run hello-go-redis.go
```
