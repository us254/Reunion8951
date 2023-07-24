Here are the steps with all commands and code blocks:

# Install Go

1. Visit Go downloads page

    ```
    https://go.dev/dl/
    ```

2. Copy download link for Linux  

3. Open Terminal

4. Download file with wget

    ```bash
    wget https://golang.org/dl/go1.20.5.linux-amd64.tar.gz
    ```

5. Extract file to /usr/local

    ```bash
    sudo rm -rf /usr/local/go && sudo tar -C /usr/local -xzf go1.20.5.linux-amd64.tar.gz
    ```

6. Add Go to PATH

    ```bash
    echo "export PATH=$PATH:/usr/local/go/bin" >> ~/.profile
    ```

7. Reload profile

    ```bash
    source ~/.profile
    ```

8. Check Go version

    ```bash
    go version
    ```

# Install Git

9. Install git

    ```bash
    sudo apt install git
    ```

# Compile Xray

10. Clone Xray repo

    ```bash
    git clone https://github.com/XTLS/Xray-core.git
    ```

11. Change to repo folder

    ```bash
    cd Xray-core
    ```

12. Download dependencies

    ```bash
    go mod download
    ```

13. Build binary

    ```bash
    go build -o xray -trimpath -ldflags "-s -w -buildid=" ./main
    ```

14. Copy binary to path

    ```bash
    sudo cp xray /usr/local/bin
    ```


# Generate Keys

15. Install openssl

    ```bash
    sudo apt install openssl
    ```

16. Generate keys

    ```bash
    openssl rand -hex 8
    ./xray uuid
    ```

# Run in Screen  

17. Install screen

    ```bash
    sudo apt install screen
    ```

18. Start screen session

    ```bash
    screen -d -m ./xray run
    ```

19. Detach from screen

20. Reattach to screen

    ```bash
    screen -r
    ```

Let me know if any part needs more explanation!
