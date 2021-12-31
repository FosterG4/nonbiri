# Nonbiri

Nonbiri is a self-hosted back-end and front-end for MangaDex.

_The UI is inspired by [Tachiyomi](https://github.com/tachiyomiorg/tachiyomi)._

## Features

---

- Online read and browse MangaDex
- Offline read and download chapters
- History tracker and scheduled updates
- Chapters and covers are automatically cached forever
- Real-time synchronization between tabs/browsers and computers
- Long strip, right-to-left and left-to-right reading modes
- Customizable keyboard shortcuts for navigating between pages and chapters

Library and history are stored locally, Nonbiri will not push follows and reading history to MangaDex for obvious reasons, but integration with third-party trackers will be added in the future.

_More features and alternative manga sources will also be added in the future._

## Installation

---

Pre-built binaries are available on [releases page](http://).

### Usage

Run `nonbiri`, then open `localhost:<port>` on your web browser.

## Compiling

---

Requirements:

- Go 1.18+
- Node.js
- Yarn

The back-end is written in Go 1.18 Beta 1 which uses generics. Please refer to the [official download page](https://go.dev/dl/) on how to download or use it.

### Building

If you are on linux, execute the following command instead:

```bash
make build build-view
```

_All output files will be inside the `bin` directory._

### Building the back-end

To build the back-end, execute the following command:

```bash
go build
```

_Note that you need Go 1.18+ to be able to compile the binary._

### Building the front-end

To build the front-end, execute the following command inside the `view` directory:

```bash
yarn && yarn prod
```

_The output files will be inside the `bin` directory._

## Local network sharing

---

Knowledge about networking is required.

If you are running the back-end on linux, simply add the port which used by the back-end into the firewall. To do so, execute the following command:

```bash
ufw allow <port>
```

Then you will be able to access the front-end through your local IP address, e.g., `192.168.x.x:<port>`.

To find out about your local IP address, execute the following command:

```bash
ifconfig | grep netmask

# Example output
inet 192.168.x.x # local IP address
inet 127.0.0.1  netmask 255.0.0.0
```

## License

---

**Nonbiri** is licensed under the [Apache License 2.0](https://www.apache.org/licenses/LICENSE-2.0).

## Disclaimer

---

The developer of this application does not have any affiliation with the content providers available.
