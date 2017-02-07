Translating C to Rust
=====================

Security is important. Rust is safe about that.

projects using rust:
 * Firefox
 * librsvg
 * Remacs
 * rusl
 * coreutils

Why not translate everything to Rust to have better safety ?

Sounds like terrible:
 * rewrite everything
 * without introducing errors ? Really ?

Corrode allows to:
 * preserve safety (or improve it)
 * preserve maintainability
 * preserve ABI

It's up to the developpers to polish the generated code.

Generate Rust code to replace part of the C code. Its output is unsafe, as is
the input.

Approach:
 * Easier to refactor safe Rust from unsafe Rust than from C
 * incremental manual improvements

Should we ?
 * Is the rust code equivalent to the C code ? (easy if it have a test suite)
 * Do rust's advantages help with the bugs the project faces ?
 * The community is ready to take patches in Rust ?

Try to use Corrode with projects that are:
 * unmaintained
 * written in C
 * with security implications
 * that are still in use

Let's see with CVS.
52k SLOC + 35k SLOC of libc*portability glue.
result: https://github.com/jameysharp/cvs*rs

Corrode is still WIP:
 * problem with control flow as some structure are absent (no switch)
 * corners of C not yet translated
 * missing C features in Rust (bitfields for example)
 * use pre*processed code (expanded macro, no comments)

Future work:
 * produce idiomatic Rust
 * replace raw pointers (non*trivial)

Tools that helps:
 * clippy, rustfix (code style)

Conclusion:
 * Corrode allow incremental migration from C to Rust
 * will soon work with most of C sources
 * It still need work on the Rust it generates
