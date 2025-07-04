
A lot is for diagrams and documentation
What is a CED diagram

they're not always standardised symbols used. information can span between pages too.

some information is inferred but not depicted. 

can have change of installation area
change of process section
change of composition

usually electricity or gas diagrams 

Symbol detection and classification is a big challenge 
you have symbols, lines and text

ML algorithm can get biased, and make inaccurate predictions for diagrams.

sometimes its' good for algorithms to produce incorrect new symbols in order to strengthen the ML in learning the correct ones.

-----
you find the symbols, create a library of them and train the ML on them 

then check the accuracy of it. you then get a report of elements found

drawing is analysed, and you get a report.

that gets translated into report of "this pipe x is found in area y etc"

Data inheritance
Find pipe description text, find closest pipe, 

reads over the image and classifies the elements.

can see if pipe serial 16, then it needs a something of 8 and that means it connects to a connector 22

specificity based on their classification, and the data inherits each other.

with the whole netlist compiled you can request information to be drawn from specific parts like vessel 1 to vessel 2

so it draws that based on what's in the netlist and the data inheritance between parts.

--------
corrosion detection is also used in ML computer vision to check the safety of like offshore sites etc

for image recognition you might need to process the colours to better identify corrosion

corrosion on powerlines too, drone footage getting processed

--------------------------

# digital img

greyscale can have 3 colour channels still

can also use thruples with 3D matrix to calculate colours, can be better for compression 
easier to navigate thru a 3D matrix even if it doesn't seem intuitive it's easier to calculate

K nearest neighbour is very fragile can defer to bias

Decision tree/ random forest had high variance, more robust, more thorough

People with radically different identifiers can share classes

NN is for extremely niche and specific classification, where there are many variables "maybe a 4 bedroom house is cheaper than a 5" etc


cleaning images can normalise the values so instead of white being 223 - 233 you can just wipe them all to the same value instead.


