# node-red-contrib-teachable-machine-cloudonly

| Version | Repo |
|:--|:--|
| 1.3.1 | Origin: https://github.com/bonastreyair/node-red-contrib-teachable-machine |
| 1.0.0 | THIS FORKED REPO |

This repository was forked from version 1.3.1 of the original repository. This is a workaround for a bug in the latest version of the original when installed on Node-RED running on virtualized PaaS (e.g. Railway, Render). Therefore, as the name "cloudonly" implies, it does not support loading model files that are locally located and will not be supported in the future.

---
---

## Install

You have two options to install the node.

- Use `Manage palette` option in `Node-RED` Menu (recommended)
  ![manage_pallete](https://user-images.githubusercontent.com/37800834/80922178-88923b00-8d7b-11ea-9fcf-ea1839bfee09.png)

- Run the following command in your `Node-RED` user directory - typically `~/.node-red`

  ```bash
  npm install node-red-contrib-teachable-machine
  ```

**Note:** If you run the command you will need to restart `Node-RED` after installation. If installation goes wrong please open a [new issue](https://github.com/bonastreyair/node-red-contrib-teachable-machine/issues).

## Node usage

### Step 1

Go to [Teachable Machine](https://teachablemachine.withgoogle.com/train/image) and follow the steps to train your custom classification model. Once trained click on the `Export Model` button.

![teachable_machine_export](https://user-images.githubusercontent.com/37800834/80190158-18b1e100-8614-11ea-9ccf-6668e49e7e2d.png)

### Step 2

Select `Tensorflow.js` format and upload your trained model (for free). Once it is uploaded, copy the generated URL.

![use_teachable_machine](https://user-images.githubusercontent.com/37800834/79056723-8431a100-7c59-11ea-9488-346f4f8e6004.png)

### Step 3

Paste the saved URL into the node configuration. That URL hosts all the information to load your trained model. Make sure you copy all the given URL including the `https://...`.

![config](https://user-images.githubusercontent.com/37800834/80922980-e8d7ab80-8d80-11ea-8c0c-89d1008455da.png)

### Step 4

In `Node-RED` send a buffered image (jpeg or png) to the node. Check the example in the `Import` section.

## Node Status Information

### Shape

- ■ `dot`: node is idle
- □ `ring`: node is working

### Color

- 🟩 `green`: model is available
- 🟨 `yellow`: preparing model
- 🟥 `red`: node error

## Requirements

- `Node-RED v2.0.0+`
- `Node.js v12.20.0+`

*Note:* MacOSX, Windows 10 and Ubuntu 18.04+ are supported as well as using official `docker nodered/node-red` [image](https://hub.docker.com/r/nodered/node-red/) based on [Alpine](https://hub.docker.com/_/alpine) image. Works with Raspberry Pi too since release [`v1.2.0+`](https://github.com/bonastreyair/node-red-contrib-teachable-machine/tags).

## Mentions

- [@dceejay](https://github.com/dceejay): who inspired me thanks to node [node-red-contrib-tfjs-coco-ssd](https://github.com/dceejay/tfjs-coco-ssd/)
