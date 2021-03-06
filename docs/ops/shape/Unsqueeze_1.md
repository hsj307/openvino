## Unsqueeze <a name="Unsqueeze"></a>

**Versioned name**: *Unsqueeze-1*

**Category**: Shape manipulation

**Short description**: *Unsqueeze* adds dimensions of size 1 to the first input tensor. The second input value specifies a list of dimensions that will be inserted. Indices specify dimensions in the output tensor.

**Attributes**: *Unsqueeze* operation doesn't have attributes.

**Inputs**:

*   **1**: Multidimensional input tensor. Required.

*   **2**: OD or 1D tensor with dimensions indices to be set to 1. Values could be negative. Indices could be integer or float values.

**Example**

*Example 1:*
```xml
<layer ... type="Unsqueeze">
    <input>
        <port id="0">
            <dim>2</dim>
            <dim>3</dim>
        </port>
    </input>
    <input>
        <port id="1">
            <dim>2</dim>  <!-- value is [0, 3] -->
        </port>
    </input>
    <output>
        <port id="2">
            <dim>1</dim>
            <dim>2</dim>
            <dim>3</dim>
            <dim>1</dim>
        </port>
    </output>
</layer>
```

*Example 2: (unsqueeze 0D tensor (constant) to 1D tensor)*
```xml
<layer ... type="Unsqueeze">
    <input>
        <port id="0">
        </port>
    </input>
    <input>
        <port id="1">
            <dim>1</dim>  <!-- value is [0] -->
        </port>
    </input>
    <output>
        <port id="2">
            <dim>1</dim>
        </port>
    </output>
</layer>
```