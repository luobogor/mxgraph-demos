Cell 可表示 root、layer、组、顶点、边

Geometry {
    x,
    y,
    width,
    height,
    relative | Boolean 作用？
}

The model acts as a transactional wrapper with event notification for all changes, whereas the cells contain the atomic operations for updating the actual datastructure.
该模型充当事务包装器，其中包含所有更改的事件通知，而单元格包含用于更新实际数据结构的原子操作。

getDefaultParent
Returns defaultParent or mxGraphView.currentRoot or the first child child of mxGraphModel.root if both are null.  The value returned by this function should be used as the parent for new cells (aka default layer).

setDefaultParent
Sets the defaultParent to the given cell.  Set this to null to return the first child of the root in getDefaultParent.

root 包含 layers
layer 包含  组、顶点、边
组 包含  组、顶点、边

