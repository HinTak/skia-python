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
