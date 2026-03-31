## Reference

- Kaggle Notebook: [Cat vs Dog CNN](https://www.kaggle.com/code/mercantl/cat-vs-dog-cnn)

## CNN Architecture

- **Input:** `180 × 180 × 3`

- **Data Augmentation:**
  - Random Flip
  - Random Rotation
  - Random Zoom

- **Preprocessing:**
  - Rescaling (pixel values → [0, 1])

- **Convolutional Blocks:**
  - Conv2D (32 filters) + MaxPooling2D
  - Conv2D (64 filters) + MaxPooling2D
  - Conv2D (128 filters) + MaxPooling2D
  - Conv2D (128 filters) + MaxPooling2D

- **Fully Connected Layers:**
  - Flatten
  - Dense (512, ReLU)
  - Dropout (0.5)

- **Output Layer:**
  - Dense (1, Sigmoid)

## Results

- **Test Accuracy:** 90%  
- **Precision:** ~90%  
- **Recall:** ~90%  
- **F1-Score:** ~90%  


## Findings

The model performed well overall and reached about **90% accuracy** on the test set. Precision, recall, and F1-score are also around 90%, which means the model is doing a good job at classifying both cats and dogs without being biased toward one class.

From the graphs, both training and validation accuracy increased steadily and stayed close to each other. This shows that the model is learning properly and not overfitting too much. The loss also decreased over time, which confirms that the training process was stable.

There were some small drops and spikes in the validation accuracy and loss during training, but this is normal and likely caused by differences between batches of images.

---

## Factors that affected the results

- **Data augmentation**  
  Helped the model handle different image variations (angles, flips, zoom), which improved performance on new data.

- **CNN layers**  
  The model was able to learn patterns step by step (edges - shapes - full objects), which helped it distinguish between cats and dogs.

- **Dropout layer**  
  Reduced overfitting and helped the model generalize better.

- **Dataset variety**  
  Images have different lighting, backgrounds, and poses, which makes the task harder but also helps the model become more robust.

- **Training process**  
  The optimizer (Adam) helped the model learn faster and more smoothly.

- **Fixing evaluation mistake**  
  At first, the results were wrong because predictions and labels were not aligned. After fixing this, the results became consistent and showed the real performance of the model.

---

## Conclusion

The model works well and can correctly classify most images. The results are reliable after fixing the evaluation issue, and the overall performance shows that the CNN learned useful features from the data.
