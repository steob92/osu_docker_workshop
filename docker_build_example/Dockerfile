FROM ubuntu:latest

# Install dependencies gcc
RUN apt-get update 
RUN apt-get install -y  g++
RUN rm -rf /var/lib/apt/lists/*

ENV NUM_STEPS=100000

# add in the files
COPY ./calculate_pi.cpp /build/calculate_pi.cpp

# compile the code
RUN g++ /build/calculate_pi.cpp -o /build/calculate_pi.o -fopenmp

CMD ["bash", "-c", "/build/calculate_pi.o ${NUM_STEPS}"]