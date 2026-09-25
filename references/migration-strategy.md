# Migration Strategy Reference

Prefer a sequence of small, independently usable migrations:

1. Characterize the current behavior.
2. Introduce a seam at an existing change point.
3. Move one behavior behind the seam.
4. Keep the old path available until the new path is verified.
5. Remove the obsolete path only after regression checks pass.

The target is a smaller change surface and clearer ownership, not a larger number of files.
