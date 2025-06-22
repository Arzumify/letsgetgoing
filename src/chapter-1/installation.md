# Getting Go

Instructions for installing Go will vary depending on your system. As such, here are different sections for all the popular operating systems.[^1]

## Linux

Despite the convenient package managers graciously provided to us by the Linux gods, we will be totally ignoring them and instead installing Go manually.

### But why?

Go updates very regularly; and as of the time this document was written, stable distros like Debian do not have a new enough version to follow in this guide. Plus, as you'll learn later, Go can update itself.

### Ok then, how do I install it manually?

Installing Go is easy! Go onto [the Go download site](https://go.dev/dl/), and download the latest tar archive for Linux.[^2]  As of time of writing, this is `go1.24.4.linux-amd64.tar.gz`.

Once you have the file downloaded, run the following commands in a terminal:

```shell
sudo -s
tar -C /opt/ -xf /path/go/go/archive.tar.xz
ln -sf /opt/go/bin/go /usr/bin/go
ln -sf /opt/go/bin/gofmt /usr/bin/gofmt
```

If everything works, running the command `go version` in your terminal should show Go coming to life!

```
go version go1.24.4 linux/amd64
```

## MacOS

Due to the numerous architecture switches Apple has made in the past few years, these steps will vary depending on your specific computer.

### Step 1

#### Apple Silicon (M1+)
Download the file ending in `.darwin-arm64.pkg` from [the Go download site](https://go.dev/dl/), then continue to step 2.

#### Intel
Download the file ending in `.darwin-amd64.pkg` from [the Go download site](https://go.dev/dl/), then continue to step 2.

### Step 2 

Once that's done, install it by double-clicking the `.pkg` file and following the on-screen instructions.

### Step 3

If everything worked, open the `Terminal` app on your computer, and run `go version`. Go should come to life!

```
go version go1.24.4 darwin/arm64
```

## Windows

For the purposes of this book, it's recommended to use WSL instead of running Go natively[^3]. However, covering WSL installation is outside of the scope of this guide, and on Windows things _mostly_ work.

Download the file ending in `.windows-amd64.msi`[^2] from [the Go download site](https://go.dev/dl/), and follow the on-screen instructions to install (just like installing any other MSI).

Once that's complete, open up a terminal of your choice (options built in involve the "Command Prompt" or "Powershell" app) and run `go version`.

```
go version go1.24.4 windows/amd64
```

If everything worked, the version dialogue will appear, and you're ready to Go!

[^1]: Except Android and iOS, because they don't feel like working.
[^2]: If your architecture is anything other than x86_64 (it probably isn't), substitute amd64 in the archive name for whatever your architecture is (probably arm64).
[^3]: Note that some of this book cannot be followed by Windows users, primarily the segments involving the `syscall` package. These will be marked out for you, and you will be able to skip past them.