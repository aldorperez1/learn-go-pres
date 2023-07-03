# Learning Go: Presentation

## Description

This project is a presentation for the `Learning Go` class in the `Cloud Native Academy` in BoxBoat.


This presentation is actually a website created using Hugo, a static site generator.

## Table of Contents

- [Learning Go: Presentation](#learning-go-presentation)
  - [Description](#description)
  - [Table of Contents](#table-of-contents)
  - [Getting Started](#getting-started)
    - [Prerequisites](#prerequisites)
    - [Installation](#installation)
  - [Usage](#usage)
  - [Deployment](#deployment)
  - [Contributing](#contributing)
  - [License](#license)
  - [Contact](#contact)

## Getting Started

These instructions will help you set up the project locally and get it running on your machine for development and testing purposes.

### Prerequisites

Before you begin, make sure you have the following installed:

- Hugo (version > 0.115.0)
- go (version > 1.19)

### Installation

1. Clone the repository:

```shell
git clone https://github.com/aldorperez/learn-go-pres.git
```

2. Change into the project directory:

```shell
cd learn-go-pres
```

3. Install the project dependencies:

```shell
hugo mod get github.com/dzello/reveal-hugo
```

4. Install plugins

To extend the functionality of the slides, I added some plugins that are installed under `static/plugins`, that need to be downloaded as git submodules using the following:

```shell
git submodule init
git submodule update
```

## Usage

To start the server in development mode:

```shell
hugo server
```

Open your browser and navigate to `http://localhost:1313` to see the website.

## Deployment

You can output a static html site that can be hosted on a webserver such as NGINX or APACHE using:

```shell
hugo
```
This will create a `public` directory that can be installed on one of said servers.

## Contributing

Let me know if you want to contribute to this project and I will add you as a contributor. Please submit a merge request and I will check it before merging into `main`.

## License

See [LICENCE](./LICENCE)

## Contact

If you have any questions, please contact me at aldo.perez@ibm.com