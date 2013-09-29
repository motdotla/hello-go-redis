# hello-go

My first program in go. An example of how to use go.

## Usage

```bash
go run hello.go
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
mkdir -p src/github/yourgithubusername
```

### Create the hello-go project

```bash
cd src/github/yourgithubusername
mkdir hello-go
cd hello-go
vim hello.go
```

Paste the following into `hello.go`.

```go
package main

import "fmt"

func main() {
  fmt.Printf("hello, go\n")
}
```

### Run it

```bash
go run hello.go
```
