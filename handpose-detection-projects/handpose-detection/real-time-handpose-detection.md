# Real Time Handpose Detection

{% embed url="https://abhyaskanaujia.github.io/Handpose-Detection-App/" %}
Deployed and live on GitHub Pages
{% endembed %}

So this is a project where we can detect hand poses and show different emojis based on the pose. I'll be following the [Real Time AI HAND POSE Estimation with JavaScript, Tensorflow.JS and React.JS](https://youtu.be/f7uBsb-0sGQ) tutorial.&#x20;

We're going to do a single hand detection and label and detect 21 key points on one hand.&#x20;

## Steps

1. Install dependencies
2. Import dependencies
3. Setup of Webcam and Canvas
4. Defining reference to those
5. Load `handpose`
6. Detect Function
7. Draw utilities from TensorFlow
8. Draw function

### Dependencies

```bash
npm i @tensorflow/tfjs @tensorflow-models/handpose react-webcam
```

1. `tensorflow.js`
2. Import hand pose model, which is a pretrained machine learning library built by the TensorFlow team
3. `react-webcam` to work with webcam

There are many pretrained models on [https://www.tensorflow.org/js/models](https://www.tensorflow.org/js/models). We're using one of these.&#x20;

![](<../../.gitbook/assets/image (3) (1).png>)

> This is the first time in my life that I'm getting to work with video. Literally the word "video" written in my source code feels exciting. I'm so happy and overwhelmed

I'm literally squealing right now. This is soooo exciting. <img src="../../.gitbook/assets/image (2) (1).png" alt="" data-size="line">

I never knew I keep smiling when I'm doing things that I love.&#x20;

What's happiness? <img src="../../.gitbook/assets/image (5).png" alt="" data-size="line">

## Completed

I've completed this project. It was really fun. Though the results are really simple, but I had a lot of fun building it. I'll deploy it to GitHub Pages now. I'll follow this tutorial. [How to Deploy React App to GitHub Pages](../../how-to-deploy-react-app-to-github-pages.md).
