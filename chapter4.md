# Transformations

## 數學仙貝（？

  ### Linear Independent
  如果向量 *$${v_1}$$*, *$${v_2}$$*, *$${v_3}$$*, ... , *$${v_n}$$* 為 Linear independent 則：
  
  當
  
  $${α_1}{v_1}+{α_2}{v_2}+{α_3}{v_3}+ ...  +{α_n}{v_n} = 0$$
  
  $${α}$$ 序組只能有唯一解，為
  
  $${α_1} = {α_2} = {α_3} = ... = {α_n} = 0$$
  
  ### Dimension
  一個Vector space當中Linear independent的向量數目稱為Dimension。
  
  

## Matrix Stack
  在做Transformations時，會不斷對Model-View Matrix做操作，在處理多個物件時，常常會需要使matrix回到前一個狀態。
  可以透過push stack將目前的matrix儲存，待操作完畢後，可以利用Pop stack進行復原(Undo)
  
  Stack 最多可以儲存32層，所有對Model-View matrix操作都是以stack最上層的matrix進行操作

## 相關資源

[Raw Slide](https://raw.githubusercontent.com/erickson-makotoki/computer-graphic-yzu/master/cg_lecture_04.pdf)
