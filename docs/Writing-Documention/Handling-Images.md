
### Where to store images (and how to reference them)

You should save images anywhere within the `docs` directory.

~~~ title="Example directory structure"
docs/
  Writing-Documentation/
    Handling-Images.md
    images/
      image1.png
      image2.png
~~~

Where they can be referenced relative to the markdown files like this:

~~~ markdown title="Markdown"
![Image title](images/cat-gurad.jpg.png)
~~~

![LeChat](./images/cat-gurad.jpg){ width="600" }
/// caption
Gurad is watching our back
///


!!! tip "Be organised!"
    Save the images in a directory close the markdown file. Put all the images for that markdown to that folder.

### Captions 

~~~ yml title="mkdocs.yml"
...
markdown_extensions:
  - pymdownx.blocks.caption
...
~~~


~~~ markdown title="Image with caption"
![Image title](https://dummyimage.com/600x400/){ width="300" }
/// caption
Image caption
///
~~~

![Image title](https://dummyimage.com/600x400/){ width="600" }
/// caption
Image caption
///