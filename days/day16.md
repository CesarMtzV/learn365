# Kerberos
___
Index | Topic
--- | ---
**1** | Description
**2** | Client 
**3** | Server

## Description

Its a way of connecting two nodes in a network to communicate with each other. One socket lists to a port at an IP, while the other socket reaches out to the other to form a connection. The server forms the listener socket while the client reaches out to the server.

## Client

### Socket creation
```c
int sockfd = socket(domain, type, protocol)
```
- Options:
  - sockfd: Socked file descriptor
  - domain: Communication domain, an integer
    - AF_INET (IPv4)
    - AF_INET6 (IPv6)
  - type: Communication type
    - SOCK_STREAM: TCP
    - SOCK_DGRAM: UDP
  - protocol: protocol value for IP, which is 0.
### Connect
```c
int connect(int sockfd, const struct sockaddr *addr, socklen_t addrlen);
```

## Server

### Socket creation

```c
int sockfd = socket(domain, type, protocol)
```

### Set socket options (OPTIONAL)
```c
int setsockopt(int sockfd, int level, int optname, const void *optval, socklen_t optlen);
```

### Bind
```c
int bind(int sockfd, const struct sockaddr *addr, socklen_t addrlen);
```

### Listen 
```c
int listen(int sockfd, int backlog);
```

### Accept
```c
int new_socket = accept(int sockfd, struct sockaddr *addr, socklen_t *addrlen);
```