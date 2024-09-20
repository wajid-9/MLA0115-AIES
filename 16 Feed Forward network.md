import tensorflow as tf from tensorflow.keras import layers, models

def build\_neural\_network(input\_size, hidden\_size, output\_size): model = models.Sequential([ layers.Dense(hidden\_size, activation='relu', input\_shape= (input\_size,)), layers.Dense(output\_size, activation='softmax') ]) return model

input\_size = 4 output\_size = 2 data\_size = 1000

x\_train = tf.random.normal((data\_size, input\_size)) y\_train = tf.keras.utils.to\_categorical(tf.random.uniform((data\_size,), minval=0, maxval=output\_size, dtype=tf.int32), num\_classes=output\_size)

hidden\_size = 64 model = build\_neural\_network(input\_size, hidden\_size, output\_size) model.compile(optimizer='adam', loss='categorical\_crossentropy', metrics=['accuracy'])

epochs = 10 batch\_size = 32 model.fit(x\_train, y\_train, epochs=epochs, batch\_size=batch\_size)

x\_new = tf.random.normal((5, input\_size)) predictions = model.predict(x\_new) print("Predictions:") print(predictions)


**output**




![image](https://github.com/user-attachments/assets/3ab5bb41-dc2b-40ba-8a13-df4f792a99db)
