Since m138:

- Vulkan APIs which used to take integer values defined as
  `VK_FORMAT_*` and `VK_IMAGE_LAYOUT_*` in vulkan c/c++ headers,
  now requires `skia.VkFormat.*` `skia.VkImageLayout.*` mnemonics.
  E.g.

  # VK_FORMAT_R4G4_UNORM_PACK8 = 1 in `vulkan_core.h`

  skia.GrBackendFormat.MakeVk(1)
      -> skia.GrBackendFormat.MakeVk(skia.VkFormat.R4G4_UNORM_PACK8)

  This is a general improvement (though not-backward compatible),
  and a workaround for a bug in pybind 3.x. Fixes runtime exit
  segfault when built against pybind 3.x.

  Reference:
  https://github.com/pybind/pybind11/issues/5991
  [BUG]: segfault at exit since upgrading to 3.0.x, probably due to
  "Make wrapped C++ functions pickleable" (https://github.com/pybind/pybind11/pull/5580)

- A far amount of under-the-hood code updates, in response
  to upstream's general move to use `SkSpan`. Not user-visible.
  Reference in m140's `RELEASE_NOTES.md`:

```
    ...now take SkSpan instead of ptr/count. This
    is part of the larger change where public APIs are being converted to take SkSpan where
    applicable.

    No real functionality change, but this new signature allows some of the methods to perform
    range-checking, whereas before they could not.
```

CI:

- updated to use `macos-14`, `macos-15-intel`, as `macos-13` is no longer
  supported in github.
