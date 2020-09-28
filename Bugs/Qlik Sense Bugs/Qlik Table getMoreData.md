## The Problem:

This function runs wrong when data length bigger qInitialHeight property and datas order by or reverse order.

<br>
<br>

## The Source of The Problem

This function gets qHeight and qTop property for gets more data. Table Api order functions order table by qInitialHeight. The problems start here.

orderFunc();
<br>
getMoreData();

<br>

This structure when runs, can not get more data and can not call another getMoreData func.
<br>

orderFunc().then(){
<br>
getMoreData();
<br>
}

This structure runs but not right, it gets datas wrong. An example: datas : 190 180 170 200 210 |(qInitialHeight)| 220 230 240 250 260
<br>
When order by, 170 180 190 200 210 it is true but when i call the getMoreData with then structure:
<br>
170 180 190 200 210 250 260.
<br>
<br>
And after i click button, it has getMoreData function. The datas:
<br>
170 180 190 200 210 250 260 220 230 240 250 260

I think the qHeight and qTop properties be wrong when call order functions. So getMoreData runs wrong when data length was bigger qInitialHeight and the table was ordered.
