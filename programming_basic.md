# 程式基本架構

根據 OpenGL Legacy 的 Pipe Line ，圖學概論使用的程式基本結構如下。

OpenGL 只負責圖形運算部分，因此大部分的API（包含視窗化、輸入輸出等）都仰賴 GLUT ( function 前綴會有 "glut" ，以下說明為了簡短，會省去 glut 的前綴詞。)

## header file
為了相容 MAC 和其他作業系統，在透過 GLUT 載入 OpenGL 時會採用以下寫法。
```
#ifdef __APPLE__
#include <GLUT/glut.h>
#else
#include <GL/glut.h>
#endif
```
利用 constant 的 define 來辨識作業系統

## Main Function架構

```
glutInit(&argc,argv);
glutInitDisplayMode(GLUT_SINGLE|GLUT_RGB);
glutInitWindowSize(width, height);
glutInitWindowPosition(x, y);
glutCreateWindow(windowTitle);
glutDisplayFunc( DisplayFunc );
glutReshapeFunc( ReshapeFunc );
```
##### init
  可以透過 command line 給予初始化參數。若不打算從 command line 輸入初始化參數則省略此設定。

  *Mac系統下不可以省略。*

##### initDisplayMode
  關於Display相關的設定值初始化，包含：
  * Frame Buffer（Single/Double)
  * 色彩空間 (通常會直接設定 RGB)

##### initWindowSize
  初始化視窗大小，單位是 px。參數依序是寬和高。

##### initWindowsPosition
  程式執行時，視窗出現的起始位置。原點在螢幕左上方。

##### CreateWindow
  實際創造出視窗程式，參數為視窗標題。

##### DisplayFunc
  設定在 Display 狀態時必須呼叫的 Function 。
  參數型態為：
```
void (fun*) (void)
```
  亦即回傳與參數皆為 void 的function。

  在Mac OS X會進入 Display 狀態的時機：
  * 視窗剛建立時
  * 縮小後再展開

##### ReshapeFunc
  設定在 Reshape 狀態時必須互叫的 Function 。
  參數型態和 DisplayFunc 相同

  在Mac OS X 會進入 Reshape 狀態的時機：
  * 視窗剛建立時
  * 視窗大小改變時
