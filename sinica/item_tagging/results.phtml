<html>
	<head>
		<meta http-equiv="Content-Type" content="text/html; charset=utf-8">

		<!-- DataTables CSS -->
		<link rel="stylesheet" type="text/css" href="../js/DataTables/media/css/jquery.dataTables.css">
		<link rel="stylesheet" type="text/css" href="../js/DataTables/extensions/FixedColumns/css/fixedColumns.dataTables.css">
		<link rel="stylesheet" type="text/css" href="../js/DataTables/extensions/TableTools/css/dataTables.tableTools.css">

		<!-- jQuery -->
		<script type="text/javascript" charset="utf8" src="../js/jquery-1.11.3.min.js"></script>

		<!-- DataTables -->
		<script type="text/javascript" charset="utf8" src="../js/DataTables/media/js/jquery.dataTables.js"></script>
		<script type="text/javascript" charset="utf8" src="../js/DataTables/extensions/FixedColumns/js/dataTables.fixedColumns.js"></script>
		<script type="text/javascript" charset="utf8" src="../js/DataTables/extensions/TableTools/js/dataTables.tableTools.js"></script>

		<!-- Simple statistics -->
		<script type="text/javascript" charset="utf8" src="../js/simple_statistics.js"></script>

		<!-- PapaParse -->
		<script type="text/javascript" charset="utf8" src="../js/papaparse.js"></script>

		<style>
			th, td {
				text-align: center;
				font-size: small;
				white-space: normal;
				word-wrap: break-word;
			}
			td.highlight {
			    background-color: mistyrose !important;
			}
			tr:hover {
			    background-color: paleturquoise !important;
			}
			tr:hover td:hover {
				background-color: papayawhip !important;
			}
		</style>

		<title>item_tagging_dev - 這是結果!</title>
		<script type="text/javascript">
			/* Custom filtering function which will search data in column round.duration.q75 between two values */
			$.fn.dataTable.ext.search.push(
			    function( settings, data, dataIndex ) {
			        var index =$('#myselect').val();
			        var min = parseInt( $('#min').val(), 10 );
			        var max = parseInt( $('#max').val(), 10 );
			        var actions = parseFloat( data[index] ) || 0; // use data for the actions column

			        if ( ( isNaN( min ) && isNaN( max ) ) ||
			             ( isNaN( min ) && actions <= max ) ||
			             ( min <= actions   && isNaN( max ) ) ||
			             ( min <= actions   && actions <= max ) )
			        {
			            return true;
			        }
			        return false;
			    }
			);

			$(document).ready( function ()
			{
				var lastIdx = null;
				var table = $('#mytable').DataTable({
					// "ordering": true,
					// "orderMulti": true // depend on ordering
					scrollX: true,
					scrollCollapse: true,
					dom: 'T<"clear">lfrtip',
					tableTools: {
						"sRowSelect": "os",
			      		'sSwfPath': '../js/DataTables/extensions/TableTools/swf/copy_csv_xls_pdf.swf',
			            "aButtons": [{
				          	"sExtends": "csv",
			              "bSelectedOnly": true,
			              "bFooter": false
			            },
			            "select_none" ]
				        }
						// "autoWidth": false,
						// 'bAutoWidth': false
				});

			  	$('#mytable tbody')
			        .on( 'mouseover', 'td', function () {
			            var colIdx = table.cell(this).index().column;

			            if ( colIdx !== lastIdx ) {
			                $( table.cells().nodes() ).removeClass( 'highlight' );
			                $( table.column( colIdx ).nodes() ).addClass( 'highlight' );
			            }
			        } )
			        .on( 'mouseleave', function () {
			            $( table.cells().nodes() ).removeClass( 'highlight' );
		      	} );

				// Event listener to the two range filtering inputs to redraw on input
			    $('#min, #max').keyup( function() {
			        table.draw();
			    } );

				// new $.fn.dataTable.FixedColumns( table, {
			 //        leftColumns: 4
			 //    } );

				$(".DTFC_LeftFootWrapper table tfoot th").each( function ( i ) {
      			var select = $('<select><option value=""></option></select>').appendTo( $(this).empty() ).on( 'change', function () {
              		var val = $(this).val();

              		table.column( i ).search( val ? '^'+$(this).val()+'$' : val, true, false ).draw();
          		} );

      			table.column( i ).data().unique().sort().each( function ( d, j ) {
	          			select.append( '<option value="'+d+'">'+d+'</option>' )
	      			} );
	  			} );

				$(".dataTables_scrollFootInner table tfoot th").each( function ( i ) {
      			var select = $('<select><option value=""></option></select>').appendTo( $(this).empty() ).on( 'change', function () {
              		var val = $(this).val();

              		table.column( i ).search( val ? '^'+$(this).val()+'$' : val, true, false ).draw();
          		} );

      			table.column( i ).data().unique().sort().each( function ( d, j ) {
	          			select.append( '<option value="'+d+'">'+d+'</option>' )
	      			} );
	  			} );

				var columns = ['time', 'bounty', 'uid', 'ip', 'duration', 'duration.round.q75', 'duration.round.med'];
	  			$('#column_selection').each( function(i) {
						var select = $('<select id="myselect"><option value=""></option></select>').appendTo( $(this).empty() ).change(function(){
								var val =$('#myselect').val();
								var col = columns[val];
								var vector = [];
								myparse.data.forEach(function(element, index, array){
									vector.push(element[col]);
								});
								console.log(vector);
								var quan = ss.quantile(vector, [0.0, 0.050001, 0.150001, 0.250001, 0.500001, 0.750001, 0.850001, 0.950001, 1.0]);
								var quan_text = ['0%', '5%', '15%', '25%', '50%', '75%', '85%', '95%', '100%'];
								var quan_output = quan;
								quan_output.forEach(function(element, index, array){
									quan_output[index] = element + '（' + quan_text[index] + '）';
								});
								$('#quantile_value').html(quan_output.join(' '));
								$('#count_value').html(vector.length);
						});
						var drops = ['time', 'bounty', 'uid', 'ip'];
						columns.forEach(function(element, index, array){
							if (drops.indexOf(element) == -1) {
								select.append( '<option value="'+index+'">'+element+'</option>' );
							}
						});
	  			} );

	  			$.ajax({ url: "user_metadata.csv", success: function(response) {
						  mycsv = response;
						  myparse = Papa.parse(mycsv, {header:true,skipEmptyLines:true});
					  }
				});

	  			setTimeout(function(){
		  			Bounty = location.search.split('=')[1];
		  			if (Bounty !== undefined) {
		  				$('#mytable').DataTable().search(Bounty).draw();
		  				$('#myselect').val(5);
	  					$('#myselect').change();
		  			}
	  			}, 100);
			} );
		</script>
		<hr>
	</head>

	<body>
		<table border="0" cellspacing="5" cellpadding="5">
      <tbody>
	      <tr>
		      <td>Column:</td>
		      <td id='column_selection'></td>
		      <td></td>
		      <td></td>
		      <td></td>
		      <td></td>
	      </tr>
	      <tr>
	          <td>minimum (range):</td>
	          <td><input type="text" id="min" name="min"></td>
	          <td>count:</td>
			      <td id='count_value'></td>
	      </tr>
	      <tr>
	          <td>maximum (range):</td>
	          <td><input type="text" id="max" name="max"></td>
	          <td>quantile:</td>
		      	<td id='quantile_value'></td>
	      </tr>
	    </tbody>
  	</table>
		<table id='mytable' class='display stripe row-border hover' cellspacing="0" width="100%" style="margin-left: 0px">
		<?php
			$path = 'user_metadata.csv';
			if(file_exists($path)) {
				$f = fopen($path, "r");

				$header = true;
				if($header){
					echo '<thead>';
					$headline = fgetcsv($f);
					echo '<tr>';
					foreach ($headline as $cell) {
						echo "<th>" . htmlspecialchars($cell) . "</th>";
					}
					echo '</tr>';
					echo '</thead>';
				}

				echo '<tbody>';
				while( ($line = fgetcsv($f)) !== false) {
					echo "<tr>";
					foreach ($line as $cell) {
						echo "<td>" . htmlspecialchars($cell) . "</td>";
					}
					echo "</tr>\n";
				}
				echo '</tbody>';
				fclose($f);

				$f2 = fopen($path, "r");
				echo '<tfoot>';
				$footline = fgetcsv($f2);
				echo '<tr>';
				foreach ($footline as $cell) {
					echo "<th>" . htmlspecialchars($cell) . "</th>";
				}
				echo '</tr>';
				echo '</tfoot>';
				fclose($f2);
			} else {
				echo "The file does not exist.<br/>";
			}
		?>
		</table>
	</body>
</html>