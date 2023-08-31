# Translating Symbolic

For an extensive explanation of the problem, see [the explanation](#explanation).

## Installing

Get it via [`cargo`](https://rustup.rs/).

```
cargo install translating-symbolic
```

To install cargo, run

```
curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh
```

## Executing

If installed via `cargo`, execute the command `translating-symbolic`.

Otherwise, you can run the program by executing `cargo run` in the root of this repository.

### Usage

The program will read input from `stdin`.
Type in a symbolic sequence in the following format:

`LR` or `L1R2` or `LRLRLRLR` or `L10R20`.
Whitespace is ignored.

On Enter, the symbolic sequence of the same cycle in the full model is displayed.
This may be two coexisting cycles.

`Ctrl-D` stops the program.

## Explanation

Suppose the model function $f$ of your dynamical system is a circle map and piecewise-smooth.
It is defined on some domain $[0, 2n]$ and has four branches $f_A, f_B, f_C,$ and $f_D$.
Suppose additionally, it has the following symmetry:

$$f(x + n) \equiv f(x) + n \mod 2n$$

This model is referred to as the full model.
The model function of the halved model is a circle map $h$, that is defined on the domain $[0, n]$ and

$$h(x) = f(x) \quad \forall \in [0, n]$$

It has only two branches that are called $L$ and $R$.

This program translates the symbolic sequences of a cycle in the halved model to its symbolic sequence in the full model.
