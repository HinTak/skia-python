Since m138:

- Vulkan APIs now take `skia.VkFormat.*` `skia.VkImageLayout.*`
  mnemonics, instead of integer values in vulkan C headers.
  (workaround for pybind11 upstream bug 5991)

- `skia.ApplyPerspectiveClip` removed upstream. Associated APIs take
  one fewer argument.

- `skia.PathBuilder.incReserve` takes one more argument.

- CI: we now build for macos-14 (up from macos-13), and also python 3.14


Since m143:

- Small addition to CI/debugging. No user-visible changes.
