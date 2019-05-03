What are Channels and Kernels (according to EVA)?
------------------------------------------------
A kernel is used to extract a particular feature from an object. Eg: vertical lines or horizontal lines or curved lines will all be 3 different kernels. Another example could be to extracting rice grains(from a prepared dish) using a rice grain kernel or extracting peas(from a prepared dish) using a pea kernel.
A channel however is like a bucket storing extracted features of a particular type. eg: all the vertical lines or all the horizontal lines extracted from a particular kernel will create a channel. Another example can be all the rice grains extracted from a dish would reside under 1 channel or all the peas extracted from a dish would reside under another channel


Why should we only (well mostly) use 3x3 Kernels?
------------------------------------------------

We have a choice to choose kernels of different sizes. A 3X3 kernel is largely used because:
1) The features that would be extracted will be more local(and less generic) in a smaller kernel than in a larger kernel.
2) The amount of information or features extracted will be more, which can be further useful in later layers.
3) NVIDIA provides better, faster and more optimised computations for a 3X3 kernel than a kernel of larger size. 


How many times do we need to perform 3x3 convolution operation to reach 1x1 from 199x199 (show calculations)
------------------------------------------------------------------------------------------------------------
199X199->197X197->195X195->193X193->191X191->189x189->187X187->185X185->183X183->181X181->179X179->177X177->175X175
173X173->171X171->169X169->167X167->165X165->163X163->161X161->159X159->157X157->155X155->153X153->151X151->149X149
147X147->145X145->143X143->141X141->139X139->137X137->135X135->133X133->131X131->129X129->127X127->125X125->123X123
121X121->119X119->117X117->115X115->113X113->111X111->109X109->107X107->105X105->103X103->101X101->99X99->97X97->95X95
93X93->91X91->89X89->87X87->85X85->83X83->81X81->79X79->77X77->75X75->73X73->71X71->69X69->67X67->65X65->63X63->61X61
59X59->57X57->55X55->53X53->51X51->49X49->47X47->45X45->43X43->41X41->39X39->37X37->35X35->33X33->31X31->29X29->27X27
25X25->23X23->21X21->19X19->17X17->15X15->13X13->11X11->9X9->7X7->5X5->3X3->1X1

So we need to perform 100 3X3 convolution operations to reach 1X1 from 199X199
