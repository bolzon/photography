# Photography

Useful scripts to be used in photography.

## Renaming

To rename files in a counter order.

```sh
$ n=1; for f in *.jpg; do mv "$f" "$(printf "AB_%04i.jpg" "$n")"; ((n++)); done
```

## ExifTool

Remove camera and lens model from exif metadata.

```sh
$ exiftool -Make= -Model= -Lens= -By-Line= \
           -LensModel= -LensInfo= -LensID= \
           -overwrite_original_in_place [FILE]
```

Add copyright info.

```sh
$ export COPYRIGHT="Alexandre Bolzon"

$ exiftool -Artist="$COPYRIGHT" -Copyright="$COPYRIGHT" \
           -Creator="$COPYRIGHT" -Rights="$COPYRIGHT" \
           -By-Line="$COPYRIGHT" -CopyrightNotice="$COPYRIGHT" \
           -overwrite_original_in_place [FILE]
```