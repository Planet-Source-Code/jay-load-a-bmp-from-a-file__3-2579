<div align="center">

## Load a BMP from a file


</div>

### Description

This is a simple, easy to use function that shows how to load a bitmap from a file then bitblit it to a window.
 
### More Info
 


<span>             |<span>
---                |---
**Submitted On**   |
**By**             |[Jay](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByAuthor/jay.md)
**Level**          |Beginner
**User Rating**    |4.2 (25 globes from 6 users)
**Compatibility**  |C\+\+ \(general\), Microsoft Visual C\+\+
**Category**       |[Graphics/ Sound](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByCategory/graphics-sound__3-15.md)
**World**          |[C / C\+\+](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByWorld/c-c.md)
**Archive File**   |[](https://github.com/Planet-Source-Code/jay-load-a-bmp-from-a-file__3-2579/archive/master.zip)





### Source Code

```
//load bmp
int LoadBitmapFile(char* FileName, int x, int y, HWND hwnd)
{
BITMAP bm;
HDC hdc = GetDC(hwnd);
BitHandle = (HBITMAP)LoadImage(NULL, FileName, IMAGE_BITMAP, 0,0, LR_LOADFROMFILE);
if(BitHandle == NULL)
{
MessageBox(0, "Error loading the specified bitmap", "Program Error!",
MB_ICONERROR | MB_SYSTEMMODAL | MB_OK);
}
HDC dc = CreateCompatibleDC(hdc);
SelectObject(dc, BitHandle);
GetObject(BitHandle, sizeof(BITMAP), &bm);
BitBlt(hdc, x, y, bm.bmWidth, bm.bmHeight, dc, 0,0, SRCCOPY);
ReleaseDC(hwnd, hdc);
return(0);
}
/* to load a bmp simple call the function as follows : LoadBitmapFile("bitmap.bmp",50,50,hwnd);
hope this helps */
```

