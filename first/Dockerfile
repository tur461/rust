# multistage docker image container

# first container 
# Create the build container to compile the hello world program
FROM rust:1.40-stretch as builder
ENV USER root
RUN cargo new hello
WORKDIR hello
RUN cargo build --release

# second container
# Create the execution container by copying the compiled hello world to it and running it
FROM scratch
COPY --from=builder /hello/target/release/hello /hello
CMD ["/hello"]
