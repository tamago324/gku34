* [Lofree スイッチ](https://www.lofree.co/products/lofree-x-kailh-full-pom-low-profile-switches)を使えるようにした
  * Choc V1 も使える
* rev0.3 との違い
  * 配線をF.cu側に集めた
    * スイッチの交換をするときに、配線に傷がつかないようにするため


## 発注するとき (JLCPCB)

* 基板
  * main_pcb (メイン基板)
    * `gerbers/main_pcb/gku34_247.632052x114.711068mm_for_JLCPCB.zip`
      * PCB Thickness: 1.6mm
      * Remove Order Number: Specify a location
  * bottom_plate (ボトムプレート)
    * `gerbers/bottom_plate/gku34-bottom-plate_247.632052x114.711068mm_for_JLCPCB.zip`
      * PCB Thickness: 1.6mm
      * Remove Order Number: Specify a location
* トッププレート
  * `stl/gku34-top-plate-jlcpcb.stl`
    * 3D Technology: MJF(Nylon)
    * Material: PA12-HP Nylon
    * Color: Black
