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



````js
// 90度正交连线样式
graph.getStylesheet().getDefaultEdgeStyle()['edgeStyle'] = 'orthogonalEdgeStyle';
````

prototype 改写的函数都无法debugger

Geometry
The width and height values are ignored for edges and the x and y values relate to the positioning of the edge label.

insertEdge 是对 createEdge、addEdge 的封装,createEdge 内部设定 `edge.geometry.relative = true`

Cell Types
There are two boolean flags on mxCell, vertex and edge, and the helper methods set one of these to true when the cell is created. isVertex(), isEdge() on mxIGraphModel are what the model uses to determine a cell's type, there are not separate objects for either type.


删除节点
graph.removeCells([state.cell]);

拖拽时显示对齐虚线
````js
// Enables guides
mxGraphHandler.prototype.guidesEnabled = true;

// Alt disables guides
mxGuide.prototype.isEnabledForEvent = function(evt)
{
    return !mxEvent.isAltDown(evt);
};
````



???
portsEnabled
mxGraph.prototype.portsEnabled
Specifies if ports are enabled.  This is used in cellConnected to update the respective style.  Default is true.
