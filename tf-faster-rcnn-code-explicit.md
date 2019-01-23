# faster rcnn architecture  
## code module  
### _build_network  
* `_image_to_head`: through vgg16/resNet(only Conv layers)etc. network,get the feature map  
*  `_anchor_component`: get the all of the anchors' coordinates in the original image and   
the number of anchors(w * h * k,here k equeals to 9)  
* `_region_proposal`:process the feature and get 2000anchors(trainging) or 300 anchors(test)  
* `_crop_pool_layer`:(Note:it does ues the RoI pooling in this faster-rcnn version,it use crop   
and resize operation refered here)crop and resize for the 256 anchors,return the anchors with  
the size 7 * 7  
* `_head_to_tail`:input the 256 anchors to fc layers and dropout layers,flaatnen to 4096  
* `_region_classification`:bbox classification and bbox regressing   
### generate_anchors  
generate all of the anchors (20000)  
* `_ratio_enum`:return  anchors through the ratios(w-h ratio)  ([1,0.5,2] in this paper)  
* `_scale_enum`:return anchors through the scales([8,16,32] in this paper)  
so through two steps above,one anchors can generate 9 anchors  
* `_mkanchors`:return the coordinates (top-left and bottom-right)of anchors  
* `_whctrs`: return the original anchors center and width and height  


