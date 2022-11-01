# Make cheat sheet

## Basics

Break line

```
target: som file \
	      other
```

## Variables

Defining a variable

```
objects = main.o mod.o
```

Referencing a variable

```
app: $(objects)
```

## Include

Include `config.mk`

```
include config.mk
```

## Prerequisites

### Order-only prerequisites

Ignore timestamps (don't create if file is newer -- useful for dirs)

```
targets : normal-prerequisites | order-only-prerequisites
```
