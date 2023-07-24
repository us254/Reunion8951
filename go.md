Here are the steps explained in more simplified terms:

# Install Go

1. Go to https://go.dev/dl/
2. Copy download link for Linux 
3. Open Terminal 
4. Use `wget` to download the file 
5. Extract the file to /usr/local
6. Add Go binary folder to PATH 
7. Reload profile file
8. Check Go version

# Install Git

9. Run `sudo apt install git`

# Compile Xray from Source

10. Clone Xray repo with `git clone https://github.com/XTLS/Xray-core.git`
11. Change to repo folder 
12. Download dependencies with `go mod download`
13. Build binary with `go build` 
14. Copy binary to /usr/local/bin

# Generate Keys 

15. Run `sudo apt install openssl`
16. Generate UUID and keys

# Run Xray in Screen

17. Install screen with `sudo apt install screen`
18. Start screen session detached 
19. Run Xray in screen 
20. Detach from screen 
21. Later reattach with `screen -r`

Let me know if any step needs more explanation or simplification! I'm happy to clarify further.
