NiceGrid
========

** NOTE ** This fork has had Nedko Ivanov's changes removed 

Description of NiceGrid /author Priyatna/

NiceGrid is a Delphi component that aimed to be a standard string grid replacement. It is written from scratch, not descended from TStringGrid. The main reason why I write this component is to have a grid component that nice and smooth. Here's some feature of NiceGrid:
  * Headers can be merged and or multilined. 
  * Smooth scrolling, not aligned to top left cell coordinate. 
  * All aspect of grid colors can be customized: header light color, header dark color, header color, grid color, text color, etc.; resulting a real nice looking grid. 
  * Alternate row color. 
  * Can be customized at design time. 
  * Each column can have its own horizontal and vertical alignment, color, and font. 
  * Each column can be hidden. 
  * Can be auto fit to width. 
  * Can be auto calculate column width. 
  * BeginUpdate and EndUpdate method for bulk cells access. 
Since it is a new component, there are several main differences between NiceGrid and TStringGrid:
  * Headers are excluded from cells, unlike TStringGrid that treats fixed rows as regular cells (Row 0, for example), Cells[0,0] in NiceGrid will access the top left editable cells, not fixed cell.

  * The only way to access the data is using Cells property or using direct array referencing style: NiceGrid1[0,0]. There are not (yet) Cols, or Rows property.

  * FixedRows -> Header, FixedCols -> Gutter. 

For sample see BasicDemo

Change history:

2018-12-28:

* Reverted NiceGrid.pas to the original version from http://www.priyatna.org/nicegrid.php
* Modified CopyToClipboard and CutFromClipboard to add tab character only if s is non-blank, since the first column in the selection may not be visible
* Modified TNiceGrid.WMHScroll and TNiceGrid.WMVScroll to use HiWord(TMessage(Msg).WParam) for the Pos value because in TWMScroll, the Pos value is a SmallInt, turning values > 32768 into a negative value




