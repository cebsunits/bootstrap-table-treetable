# bootstrap-table-treetable


#Usage
```html
<script src="src/bootstrap-table-treetable.js"></script>
```

#Options
###treetable
* type: Boolean
* description: Set true to allow the treetable in one column.
* default:  false 



#Example
```html
var $table=$('.table');
$table.bootstrapTable({ 
      url: 'your url', 
      pagination : true,
      sidePagination : "server",
      columns: [ 
      		  { field: '_state', checkbox: true}, 
                  { title: 'root', field: 'id',  expanded:true}, 
                  { title: 'title', field: 'title'}  
               ] 
  }); 

$table.on('treetable-expand.bs.table', 
    function(self,name,row) {
	$.getJSON(url,function(data){
	$table.bootstrapTable('addTreeNode', {row: data.rows}); 
	})
    });

```
