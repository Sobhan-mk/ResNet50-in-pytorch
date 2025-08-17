this file has three torch modules
first one is created for residual units implementation. residual units are pre-activated. there is a skip projection for matching the shape of input_channels and size with output of every individual residual units. 
second one is for creating blocks. first unit is every block has in channels and mid channels and stride that is 2 if needed. other units after first one in every block is a normal unit with same channes and size as input and output. 
third one is for creating all resnet structure. we have four blocks with (3, 4, 6, 3) units for blocks. this resnet is customed for hovernet. so two last blocks doesnt have stride 2 and doesnt change the shape of picture. 
we have a step with 7x7 convolution and stride 2 and a maxpool layer with stride 2. in all we have output stride = 4 in stem. we have another stride in second block that is 2. so we have output stride = 8 in whole network. 
we have reduced the output stride for implementing segmentation in hovernet. 
