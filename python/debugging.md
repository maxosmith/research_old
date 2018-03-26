# Debugging
TODO, but will be a collection of tips for debugging machine learning code.

- Overfit on small dataset.
- Ensure all variables in graph change.
  ```python
  before = sess.run(tf.trainable_variables())

  # Training step of model.

  after = sess.run(tf.trainable_variables())
  for b, a in zip(before, after):
      assert (b != a).any()
  ```
- Non-zero loss.
  ```python
  assert loss != 0
  ```
