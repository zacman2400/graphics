<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tfg.image.matting.loss" />
<meta itemprop="path" content="Stable" />
</div>

# tfg.image.matting.loss

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="https://github.com/tensorflow/graphics/blob/master/tensorflow_graphics/image/matting.py">View
source</a>

Computes the matting loss function based on the matting Laplacian weights.

```python
tfg.image.matting.loss(
    matte,
    weights,
    name=None
)
```

<!-- Placeholder for "Used in" -->

Computes the matting loss function based on the `weights` generated by the
`laplacian_weights` function which implements the approach proposed by Levin et
al. in "A Closed Form Solution to Natural Image Matting".

#### Args:

*   <b>`matte`</b>: A tensor of shape `[B, H, W, 1]`.
*   <b>`weights`</b>: A tensor containing the Laplacian weights computed by the
    `laplacian_weights` function.
*   <b>`name`</b>: A name for this op. Defaults to "matting_loss".

#### Returns:

A tensor containing a scalar value defining the matting loss.

#### Raises:

*   <b>`ValueError`</b>: If the last dimension of `matte` is not 1. If `matte`
    is not of rank 4. If the last two dimensions of `weights` are not of the
    same size. If `weights` is not of rank 5. If `B` is different between
    `matte` and `weights`.