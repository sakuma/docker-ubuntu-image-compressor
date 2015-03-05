For compressing the image(JPEG, PNG) file
=========================================

# PNG

```
docker run -v $(pwd):/working docker_image pngquant --speed 1 --output /working/converted.png /working/target.png
```



`-v $(pwd):/working` は dockerのコンテナーと、ホストマシン間でファイル(ディレクトリ)共有をするために、volumeをマウントしています。
`docker_image` : dockerをbuildしたときのimage_nameです。


# JPEG 圧縮

```
 docker run -t trusty/image jpegoptim --max=80 --dest=converted_directory target.jpeg
```

docker run -v $(pwd):/working trusty/image jpegoptim --max=80 --dest=/working/converted_directory /working/5X4PTkNOqlQjGzWEhR20-fSemkTl5sbpnBGZD8FrH.jpeg

* [option] --dest
  * 変換ファイルの格納先
  * 指定がない場合はファイルを上書きする
