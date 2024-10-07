# File Transfer Protocol (FTP)

FTP is a network protocol used to transfer files from one host to
another over a TCP connections. Compared to [HTTP](../133/README.md), 
when a connection is established, a prompt is displayed to the user
terminal in which commands can be entered to interact with the server.
It allows to use standard UNIX command, such as `ls` and `cd`, to
interact with the server.

## Connecting to a FTP server

To connect to a FTP server, you can use the `ftp` command followed by
the server's IP address or domain name, and the port:

```bash
ftp user@ftp.example.com:21
```

## Secure connection (SFTP)

To connect to a FTP server using a secure connection, you can use the
`sftp` command which uses the SSH protocol:

```bash
sftp -P 22 user@ftp.example.com
```

## Commands

`get`: Download a file from the server
`put`: Upload a file to the server
`ls`: List files in the current directory
`cd`: Change directory
`pwd`: Print working directory
`quit`: Close the connection

