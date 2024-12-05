# Rust Raw Pointer Vector Modification Bug
This repository demonstrates a potential bug when using raw pointers to modify Rust vectors. Modifying a vector's elements directly via a raw pointer can lead to undefined behavior if the vector is reallocated.

The `bug.rs` file contains the buggy code.  The `bugSolution.rs` demonstrates a safe alternative using proper vector manipulation techniques.

**Bug Description:**
The example uses `as_mut_ptr()` to obtain a raw pointer to the vector's data.  If the vector's capacity is exceeded and it needs to reallocate, the pointer becomes invalid, resulting in data corruption or a program crash.

**Solution:**
The solution avoids raw pointers.  Instead, it uses standard vector indexing (`v[0] = 4;`) for safe modification of vector contents. This ensures that memory management is handled correctly and prevents undefined behavior.