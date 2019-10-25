# graalvm-native-image-scala-example

## Usage
```
sbt assembly
docker run --rm -it -v `pwd`/target/scala-2.13:/work shomatan/graalvm-native-builder --no-fallback --initialize-at-build-time -cp main.jar Main -H:Name=app

# test
docker run --rm -it --entrypoint bash -v ${PWD}/target/scala-2.13/app:/work/app shomatan/graalvm-native-builder
./app
```