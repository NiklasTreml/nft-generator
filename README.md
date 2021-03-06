# NFT Generator

Simple Rust script for generating nfts

## Usage

Create a folder, for example ./NFT.
This folder will hold your source files.

Structure it like this for example:

```

NFT/
├─ 0-Background/
├─ 1-Body/
├─ 2-Eyes/
├─ 3-Mouth/

```

Every image will be generated by picking a random image from **every** folder. The names of the folders are used to figure out the layers of every image. They are sorted by the numbers in the beginning, low to high. In the example this would result in an image layered like this:

```
Mouth
Eyes
Body
Background
```

For ideal results, the images should be pngs with transparent backgrounds and same size, for example all of them could be 400x400 Pixels. This is necessary because the images are not centered, they are all just placed at 0x0, which is the top left.

The easiest way to make them is by creating everything as layers in photoshop and already grouping the images accordingly. Then use [this script](https://github.com/antipalindrome/Photoshop-Export-Layers-to-Files-Fast/tree/v2.6.0) to export them to the desired folder structure.

Then just run the program:

`cargo run --release <NUM_NFTS> <SRC_FOLDER> <NUM_THREADS>`

### Example

`cargo run --release 1000 .\NFT_Source\ 16`

## Notes

Script is _very_ alpha, i.e. spotty error handling to put it lightly.
