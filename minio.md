# MINIO Cheat Sheet

## Installing MINIO with Docker
```
docker pull minio/minio
docker run -d -p 9000:9000 \
  -v /mnt/data:/data \
  -e MINIO_ACCESS_KEY=mysecretaccesskey \
  -e MINIO_SECRET_KEY=mysecretkey \
minio/minio server /data
```

## MINIO CLient

### Installing client on macOS (with Homebrew)
```
brew install minio/stable/mc
mc --help
```

### Adding new Host
```
mc config host add minio http://localhost:9000 mysecretaccesskey mysecretkey --api S3v4
```