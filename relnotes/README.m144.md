v144.1:

- CI: adding Python 3.15 wheels

- Transfer to skia-python org from @kyamagu's account.

- M44 constructors and methods
  - Needs some partial setters, getters / viewers, and tests. The getters and
    setters rc and setRC should be bound to python's __getitem__ .

- Binding the TextStyle and StrutStyle height accessors
  - Needs regeneration / verification of the pngs and base64 data of png.

- Throw exception if memory backstore smaller than Pixmap info's expected size
  - Further work in similar APIs/areas needed

- Binding SkFontScanner
  - Further work needed


From v144.0.post1 to  v144.0.post2:

- Reverse upstream PNG change to fix m144 regression (#362) with
  `Paint.setShader(image.makeShader(...))`

- CI: Adding Python 3.14 Free-Threading (PEP 703 / cp314t) to build matrix


From v144.0 to v144.0.post1:

- bumped version for incomplete v144.0 pypi upload

- CI: bumped cibuildwheel version for more reliable CI provisioning.


Since m138:

- Vulkan APIs now take `skia.VkFormat.*` `skia.VkImageLayout.*`
  mnemonics, instead of integer values in vulkan C headers.
  (workaround for pybind11 upstream bug 5991)

- `skia.ApplyPerspectiveClip` removed upstream. Associated APIs take
  one fewer argument.

- `skia.PathBuilder.incReserve` takes one more argument.

- CI: we now build for macos-14 (up from macos-13), and also python 3.14

- Updates the project to Skia milestone m144, aligning Python
  bindings/tests/CI with upstream API changes (SkSpan-based signatures,
  overload disambiguation). Not user-visible.

Since m143:

- Small addition to CI/debugging. No user-visible changes.
