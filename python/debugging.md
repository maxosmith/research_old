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
- https://github.com/williamFalcon/DeepRLHacks
- `sess.graph.finalize()` if getting slightly slower, will throw errors when operations are being added over time.
- http://cs231n.github.io/neural-networks-3/#baby
  Keep track of the update magnitude and the weight-value magnitudes. The ratio of these should be reasonable (1e-3).