# Graphics Programming

[Slides](slides/cglecture_02_v3.pdf)

僅介紹 OpenGL Legacy （泛指 OpenGL 2.0 以下版本）

## Library 介紹

### OpenGL Library
OpenGL 的核心程式庫，具有跨平台特性，在 Windows 、 Linux 和 OS X 上都有對應的釋出版本。

OpenGL 主要提供以下功能(其餘依賴GLUT來達成)

* 繪圖 （點線面）
* 狀態變化 (屬性變化、旋轉、移動等)

由於發展初期仍處於硬體效能不足的時代，為了確保程式效能，捨棄物件導向架構，因此不具物件導向特性。

程式流程採狀態機模式，OpenGL會逐項狀態執行程式碼。

**_只負責圖形處理功能，不包其他功能，例如接收Input Device訊息、產生視窗程式等_**

### OpenGL Utility Library (GLUT)

用來補足 OpenGL 除了圖形處理以外的功能，像是：

* 接收 Input Device 訊息 (ex. Mouse and Keyboard )
* 提供視窗程式相關功能（連結作業系統上對應的視窗API）
* Event-driven
* 不同平台上的視窗程式結果可能有差異。

### Function 命名規則

Library Name + Function Name + 2/3 (2D or 3D or 4D) + Params Type (+ v)

Library Name :
* glut = GLUT 提供
* gl = OpenGL 內建

Params Type :
* i = int (GLint)
* f = float (GLfloat)
* d = double (GLdouble)
* s = short (GLshort)

function最後加上`v`表示參數以Array方式讀入
