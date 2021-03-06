#โครงสร้างข้อมูลแบบ JSON
โครงสร้างข้อมูลแบบ JSON เป็นโครงสร้างอีกรูปแบบหนึ่งเป็นทางเลือกจากที่นิยมใช้เช่นโครงสร้างแบบ XML และโครงสร้างที่น่าสนใจอีกแบบชื่อ [Protocol Bufers](https://developers.google.com/protocol-buffers/) 

# รูปแบบ
`object` (วัตถุ) เป็นข้อมูลที่ใช้อ้างถึงเซตย่อยกำหนดขอบเขต `object` ด้วยเครื่องหมาย `{` และ `}` ภายในวัตถุ มีชื่อและค่าสำหรับชื่อนั้น (name/value) ซึ่งแต่ละชื่อ `name` กำหนดด้วย `name` ตามด้วย `:` และ `value` หากมีหลายชื่อใช้เครื่องหมาย `,` คั่น
 
JSON ใช้ใน CASDK ตัวอย่างโค้ด

```json
  require: {
        js: [],
        css: ['app.css'],
        images: {
           world: 'images/world.png'
        },
    },
```

โครงสร้างด้านบนมี `object` ชื่อ `require` และตามด้วยเครื่องหมาย `:` ภายในมีข้อมูลชุดหนึ่ง มีชื่อ 

* js
* css
* images

ทั้งหมดคั่นด้วยเครื่องหมาย `,` 

### ภาพจาก http://www.json.org/ 

* object

![object](http://www.json.org/object.gif)

มอง `object` เป็นเซตใหญ่ของเซตโครงสร้างข้อมูลที่มีของ json ซึ่งการเขียนโค้ด `object` มีรูปแบบในภาพด้านบน 

* array

![array](http://www.json.org/array.gif)

`array` เรียกใช้ข้อมูลเป็นลำดับได้ ข้อมเริ่มนับจากเครื่องหมาย `[` สิ้นสุดเมื่อ `]` แบ่งชุดข้อมูลด้วยเครื่องหมาย `,` 

* value

![value](http://www.json.org/value.gif)

`value` เขียนโค้ดเป็น 2แบบเป็นแบบ string กับไม่เป็น string ข้อมูลแบบ string ใช้เครื่องหมาย `"` (double quote) เปิดและปิด ข้อมูลอื่นไม่ต้องการเครื่องหมาย

* string

![string](http://www.json.org/string.gif)

`string` เป็นข้อมูลมีลำดับ ใช้ `"` กำหนดขอบเขต มีเครื่องหมาย `"` และ `\` เป็นเครื่องหมายควบคุม ถ้าจะใช้ `string` ที่มีค่า `\` จะต้องเทียบกับ unicode ว่า `\` มีค่าเป็นค่าใด จึงนำมาใช้ได้ 

* number

![number](http://www.json.org/number.gif)

รูปแบบ `number` คล้าย C 

#Object ใน javascript
`object` ใน javascript มีโครงสร้างเช่นเดียวกับ JSON ตัวอย่างเช่นสร้าง `object` รถยนต์ตั้งชื่อว่า`cars` กำหนดโครงสร้าง `cars` ประกอบด้วย

* ชื่อรถ `name`
* โมเดล `model`
* น้ำหนัก `weight`
* สี `color`

คุณสมบัติด้านบนเรียกว่า **properties** จากนั้นกำหนดว่าวัตถุทำงานอย่างไร กำหนดชุดสั่งงานได้ดังนี้

* สตาร์ทรถ `start()`
* ขับ `drive()`
* เบรค `brake()`
* ดับเครื่อง `stop()`

เรียกชุดสั่งงานนี้ว่า **methods**  

ตัวอย่างโค้ดการกำหนดค่า **properties** 

```javascript
var car = {type:"Fiat", model:"500", color:"white"};
```
## JavaScript Object Methods
**methods** เป็นชุดคำสั่ง มีรูปแบบดังนี้

* ประกาศ method

```javascript
methodName : function() { code lines }
```

* โค้ดใช้งาน

```javascript
objectName.methodName()
```

* โค้ดตัวอย่างรวม **properties** และ **methods**

จากวัตถุ `cars` ด้านบน กำหนด **properties** และ **methods** ดังนี้

```javascript
cars = {
	name: "Mazda",
	model: "MAZDA2 Skyactiv-D",
	weight: "1200",
	color: "Red",
	start: function(){
		console.log("start engine");
	},
	drive: functino(){
		console.log("driving");
	},
	break: function(){
		console.log("break");
	},
	stop: function(){
		console.log("stop engine");
	}
};	
```

## ตัวอย่างการใช้ JSON

จากตัวอย่างออกแบบโครงสร้างข้อมูล `cars` ได้ดังนี้

```JSON
{
   "cars": [
	
      {
         "id":"01",
         "name": "Mazda",
         "model": "MAZDA2 Skyactiv-D",
         "weight": "1200",
         "color": "Red"
      },

      {
         "id":"07",
         "name": "Mazda",
         "model": "MAZDA2 Skyactiv-G",
         "weight": "1200",
         "color": "White"
      }
   ]
}
```
* คำสั่งใช้งาน

```HTML
<html>
   <head>
      <title>JSON example</title>
		
      <script language = "javascript" >
  
         var car1 = { "name" : "Mazda", "color"  : "Red" };
         document.write("<h1>ตัวอย่างการใช้ JSON</h1>");
         document.write("<br>");
         document.write("<h3>name = " + object1.name+"</h3>");  
         document.write("<h3>สี = " + object1.color+"</h3>");   

         var car2 = { "name" : "Mazda", "color"  : "White" };
         document.write("<br>");
         document.write("<h3>name = " + object2.name+"</h3>");  
         document.write("<h3>color = " + object2.color+"</h3>");   
  
         document.write("<hr />");
         document.write(object2.name + " เป็นรถอยู่ในโครงการ Eco Car Phase 2 " + " มีรุ่นท๊อปสี " + object2.color);
         document.write("<hr />");
  
      </script>
		
   </head>
	
   <body>
   </body>
	
</html>
```


#อ้างอิง
* [www.json.org](http://www.json.org/)
* [JavaScript Objects](http://www.w3schools.com/js/js_objects.asp)