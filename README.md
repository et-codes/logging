# Logging

A simple logging package with 5 levels:
* Debug
* Info
* Warning
* Error
* Off - only Fatal messages are shown

I wrote this to use in my personal projects with Go versions earlier than v1.21. For Go v1.21 and later, the [slog](https://go.dev/blog/slog) package does this and more.

Example usage:
```Go
package main

import "github.com/et-codes/logging"

var logger = logging.NewLogger(logging.LevelInfo)

func main() {
    logger.Info("Hello, %s", "world")
    logger.SetLevel(logging.LevelDebug)
    logger.Debug("This is a debug message")
    logger.SetLevel(logging.LevelOff)
    logger.Warning("Now all messages are supressed.")

    logger.Fatal("Fatal messages are always visible, and os.Exit(1)")
}
```