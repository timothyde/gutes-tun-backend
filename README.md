# Prerequisites

In order to get started, you need to install docker and Prisma.

Get docker from the [Docker](https://www.docker.com/products/docker-desktop) website.
Install Prisma via

```
npm i -g prisma
```

# Getting started

## Prisma

To prepare a development setup, first run the docker image containing Prisma.

```
cd prisma
docker-compose up -d
prisma deploy -e ../config/dev.env
```

This launches the Prisma Backend at port 4466. There's no need to manually connect to this endpoint though.

## Node Backend

To run a development build, go back to the root directory and install the dependencies

´´´
npm i
´´´

Once that's done, run

```
npm run dev
```

Once that's done, you'll have nodemon watching your files and re-building them, while your backend is up at port 4000. Go to http://localhost:4000/ in your browser to explore the API in GraphQL Playgrounds.

# Example Queries

To retrieve all requests run the following query

```
query requests {
  requests {
    id
    title
  }
}
```

To create a request run a mutation along the lines of

```
mutation createRequest {
  createRequest(
    data: {
      name: "Such Post Wow"
      email: "wow@wow.wow"
      phone: "+491231234567"
      address: "Wow Square 1337, 1234 Wow"
      title: "Wow"
      text: "Lorem ipsum dolor sit amet, consetetur sadipscing elitr, sed diam nonumy eirmod tempor invidunt ut labore et dolore magna aliquyam erat, sed diam voluptua. At vero eos et accusam et justo duo dolores et ea rebum. Stet clita kasd gubergren, no sea takimata sanctus est Lorem ipsum dolor sit amet. Lorem ipsum dolor sit amet, consetetur sadipscing elitr, sed diam nonumy eirmod tempor invidunt ut labore et dolore magna aliquyam erat, sed diam voluptua. Wow"
    }
  ) {
    id
  }
}

```
