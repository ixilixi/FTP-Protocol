# FTP-Protocol
*Basics of FTP

## 🔴1. Definition

FTP (File Transfer Protocol) is one of the oldest and most widely used network protocols for transferring files between computers over a TCP/IP network, such as the Internet.

It operates on a client-server model:

FTP client → initiates the connection and requests file operations.

FTP server → listens for requests, authenticates users, and handles file storage/retrieval.

## 🔴2. Basic Operation

FTP uses two separate channels between client and server:
 
| Channel Type     |                                   TCP Port  |                                                     Purpose     |
| :---             |                               :----:        |                                                            ---: |
| Command Channel  |               21                            | Used for sending commands (like USER, PASS, LIST, RETR, etc.)   |
| Data Channel     | 20 (active mode) / random (passive mode)    | Used for actual file transfer or directory listing              |

## 🔴3. Connection Modes

There are two main modes:

### 1. Active Mode

The client opens a random port and sends it to the server via the command channel.

The server then connects back to that port from its port 20.

Often blocked by firewalls (since the server initiates a connection back to the client).

### 2. Passive Mode (PASV)

The server opens a random port and tells the client which one.

The client initiates both connections (command + data), making it more firewall-friendly.

Preferred in most modern setups.
