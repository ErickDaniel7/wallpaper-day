<div align="center"><h3>🌠 Wallpaper of the Day</h3></div><br>

<!--START_SECTION:update_image-->
<img src=https://raw.githubusercontent.com/DenverCoder1/minimalistic-wallpaper-collection/main/images/totalcoconut-midjourney-landscape-wallpaper.jpg height=100% width=100% align=center alt=Daily Wallpaper />
<!--END_SECTION:update_image-->
```

5. Go to Workflows menu (mentioned in step 1), click `Update Image Readme`, click `Run workflow`.
6. Go to your non-profile readme page, you will be able to see a random image from your collection of images.

---

### Examples

1. If you want to use this action for a README that is not present in current workflow repository.

```yml
- uses: siddharth2016/update-readme-image@main
  with:
    GH_TOKEN: ${{ secrets.GH_TOKEN }}     # Needed if README repository is not profile repo
    README_REPOSITORY: <username>/<differentrepo>
```

Using `README_REPOSITORY` will change README present in that repository head.

For example, if your workflow is present in `<username>/repo1` and you want to update README present in `<username>/repo2`, then assign `README_REPOSITORY` to `<username>/repo2` in workflow at `<username>/repo1`.

2. If your images are present in a different repository than current workflow repository.

```yml
- uses: siddharth2016/update-readme-image@main
  with:
    GH_TOKEN: ${{ secrets.GH_TOKEN }}     # Needed if README repository is not profile repo
    README_REPOSITORY: <username>/<differentrepo>  # Needed if README repository is not current repo
    IMG_PATH: <your-image-directory>        # Needed if images are not present in .github/images of image repository
    IMG_REPOSITORY: <username>/<imagerepo> 
```

It's better to have all images in `.github/images` to avoid any confusion and keep the images in same repository as of README and workflow repository.

3. If you want to set image alt, height, width and alignment, then use these flags:

```yml
- uses: siddharth2016/update-readme-image@main
  with:
    GH_TOKEN: ${{ secrets.GH_TOKEN }}     # Needed if README repository is not profile repo
    README_REPOSITORY: <username>/<differentrepo>  # Needed if README repository is not current repo
    IMG_PATH: <your-image-directory>        # Needed if images are not present in .github/images of image repository
    IMG_REPOSITORY: <username>/<imagerepo>  # Needed if images are not present in current repo
    HEIGHT: 180px       # default
    WIDTH: 180px        # default
    ALIGN: right        # default
    IMG_ALT: Profile Image      # default
```

4. You can specify a commit message to override the default _"Update Readme Image"_.

```yml
- uses: siddharth2016/update-readme-image@main
  with:
    GH_TOKEN: ${{ secrets.GH_TOKEN }}     # Needed if README repository is not profile repo
    README_REPOSITORY: <username>/<differentrepo>  # Needed if README repository is not current repo
    IMG_PATH: <your-image-directory>        # Needed if images are not present in .github/images of image repository
    IMG_REPOSITORY: <username>/<imagerepo>  # Needed if images are not present in current repo
    HEIGHT: 180px       # default
    WIDTH: 180px        # default
    ALIGN: right        # default
    IMG_ALT: Profile Image      # default
    COMMIT_MESSAGE: <your-commit-message>       # default - Update Readme Image
```

---

### Tests

To run tests simply execute the following in the directory containing `main.py`:

```bash
python -m unittest discover
```

---

#### Another intriguing action you would want to use - [quote-readme](https://github.com/ErickDaniel7/quote)

#### If you liked this Action and want to contribute to upgrade this utility, please create an issue or throw a PR !
