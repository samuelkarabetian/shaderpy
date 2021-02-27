# Shaderpy

A small shader library for Pyglet.

## Documentation

Creating a shader:

```python
shader = shader.Shader(
  [
    ('shaders/color.vs', GL_VERTEX_SHADER),
    ('shaders/color.fs', GL_FRAGMENT_SHADER)
  ])
```

Binding and unbinding a shader:

```python
shader.bind()
# Render awesome stuff
shader.unbind()
```

Example of different ways of setting uniforms:

```python

matrix = [1.0, 0.0, 0.0, 0.0,
          0.0, 1.0, 0.0, 0.0,
          0.0, 0.0, 1.0, 0.0,
          0.0, 0.0, 0.0, 1.0]
matrix2 = numpy.array(matrix)
matrix3 = numpy.matrix(matrix)

shader.set_uniform('MyFloat', 42.0)
shader.set_uniform('MyVector', 1.0, 0.0)
shader.set_uniform('MySecondVector', [1.0, 2.0, 3.0])
shader.set_uniform_matrix('MyMatrix', matrix)
shader.set_uniform_matrix('MySecondMatrix', matrix2)
shader.set_uniform_matrix('MyThirdMatrix', matrix3)

```

Deleting a shader:
```python
shader.delete()
```

## Installation

```
pip install shaderpy
```
