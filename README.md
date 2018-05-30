micro-PoC for buildroot based container images.



QuickStart:
```
mkdir buildroot-test
cd buildroot-test/

git clone https://git.buildroot.org/buildroot
git clone https://github.com/jrb/buildroot-docker

cp buildroot-docker/redis/redis_defconfig buildroot/configs
cd buildroot
make redis_defconfig
make
<...go for coffee...>

cp output/images/rootfs.tar ../buildroot-docker/redis/
cd ../buildroot-docker/redis/
docker build --tag redis .

docker run -it redis:latest
```

Eventually this should be converted to a buildroot external, with the dockery bits integrated through post-scripts.
