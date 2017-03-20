# AUTO ROTATE IMAGES

If you have a web site where users can upload photos, you have a trouble. Photos taken with a smart phone or digital camera can include some EXIF data, which make an image to be rotated 90ยบ, 180ยบ or 270ยบ, so the image will appear rotated in the web page, even if it looked to be fine when uploaded.

You can use `class.ExifCleaning.php` to clean exif metadata, so the image will appear properly.

First, you must include this class in the script which gets the user image and stores it on the server disk:
`include ("path_to_the_class_file/class.ExifCleaning.php");`

The you must be sure the path to the image file, and the image file itself are Apache writeable. I gues they are, or you couldn't save the image with `move_uploaded_file()`.

Now (once the image is saved onto the disk) write a sentence like this one:
```
ExifCleaning::adjustImageOrientation("path_to_the_image_file/image_file.jpg"); // Most of the smartphones / digital cameras images are jpg type.
```

Thats all. Now EXIF rotating metadata are removed, and the image will be properly rendered in your site.

This version supports jpg, gif, png or bmp images.

You can read more (in spanish) on https://eldesvandejose.com/2017/02/21/rotacion-automatica-de-imagenes/
