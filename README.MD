<h1>C# GUI Base</h1>

<p><br />
Simple menu base, based on GTAV NativeUi or others modmenus, to use on your hack tool<br />
I&#39;ll not work on this anymore, so fell free to use and make your own changes...<br /><br />
Preview <a href="https://youtu.be/KHu8Pupnqcc&amp;nbsp">here</a>   (TIP:This video is outdated, new version have more features and options)</p>

<p><br />
<strong>Features:</strong></p>

<ul>
	<li>ModMenu Layout</li>
	<li>Easy to modify values</li>
	<li>1 pre maded menu with all options possible</li>
	<li>You can change top and background color</li>
	<li>Support any game (you need game bytes, of course)</li>
</ul>

<p><strong>TIP: All examples down here, is on source code</strong></p>

<hr />
<p><br />
<strong>How to setup your menu allways on top (from another windows)</strong><br />
</p>

```C#
FrontEver(true);
```

<hr />
<p><br />
<strong>Change form opacity:</strong></p>

```C#
Transparency(0.80); //Default is 100.0f
```

<hr />
<p><br />
<strong>How to modify top text, pos, size and color:</strong></p>

```C#
AddTitle(ID, Texto, PosX, PosY, TamX, TamY, CorR, CorG, CorB)
// System.Windows.Forms.Button ID // Button ID 
// string Texto // Top text 
// int PosX = -1 // Pos X on screen 
// int PosY = -1 // Pos Y on screen 
// int TamX = 302 // Size X on screen 
// int TamY = 60 // Size Y on screen 
// int CorR = 0 // Color RGB ID Red 
// int CorG = 0 // Color RGB ID Green 
// int CorB = 200 // Color RGB ID Blue 
```

<hr />
<p><br />
<strong>How to resize size, to add more than 3 options</strong></p>

```C#
Definir_Tamanho(100, 100, 300, 240); 
//X pos 
//Y pos 
//X size 
//Y size   
```
<em><strong>Options size Y layout:</strong></em></p>

```C#
//TIP: If you resize this, remember to resize options too 
Definir_Tamanho(100, 100, 300, 120); // 1 option 
Definir_Tamanho(100, 100, 300, 180); // 2 options 
Definir_Tamanho(100, 100, 300, 240); // 3 options 
Definir_Tamanho(100, 100, 300, 300); // 4 options 
Definir_Tamanho(100, 100, 300, 360); // 5 options 
Definir_Tamanho(100, 100, 300, 420); // 6 options 
Definir_Tamanho(100, 100, 300, 480); // 7 options 
Definir_Tamanho(100, 100, 300, 540); // 8 options 
Definir_Tamanho(100, 100, 300, 600); // 9 options 
Definir_Tamanho(100, 100, 300, 660); // 10 options 
```

<hr />
 
<strong>How to add option:</strong></p>

```C#
AddOption(button2, "Msg Option", -1, 60); // ButtonID, Screen text, posX, posY 
```
<br />
<em><strong>Add options Y pos:</strong></em></p>
  
```C#
//Add poy + 60 for another option 
//TIP: You can resize all options how you want, but remember to modify all parameters 
AddOption(button2, "Option 1", -1, 60); 
AddOption(button3, "Option 2", -1, 120); 
AddOption(button4, "Option 3", -1, 180); 
AddOption(button5, "Option 4", -1, 240); 
AddOption(button6, "Option 5", -1, 300); 
AddOption(button7, "Option 6", -1, 360); 
AddOption(button8, "Option 7", -1, 420); 
AddOption(button9, "Option 8", -1, 480); 
AddOption(button10, "Option 9", -1, 540); 
AddOption(button11,"Option 10", -1, 600); 
```

<hr />
<p><br />
<strong>How to add bool option:</strong></p>

<p></p>

```C#
AddBool(button3, "Bool Option", boolteste, -1, 120); // buttonID, Screen text, bool variable, posx, posy 
```

<p><br />
<em><strong>How to change bool status:</strong></em></p>

```C#
//You need loop this 
if (GUI.Clicou_Button_2) //Define your button ID 
{ 
	GUI.Clicou_Button_2 = false; // Change button text to OFF 
	boolteste = !boolteste; // Invert bool value 
	AddBool(button3, "Bool Option", boolteste, -1, 120, 316, 60); // Refresh option 
} 
```

<hr />
<p><br />
<strong>How to add Float option:</strong></p>

```C#
AddFloat(button6, "Float Example", ExemploFloat, -1, 300); 
```

 
<em><strong>How to change float values:</strong></em><br />
	
```C#
public static float ExemploFloat = 1.50f; 
public static float ExemploFloatMax = 10.0f; 
public static float ExemploFloatMin = 0.0f; 
public static float ExemploFloatStep = 0.53f; 
//Loop this above 
if (GUI.Clicou_Button_6)
{
	GUI.Clicou_Button_6 = false;
	if (ExemploFloat >= ExemploFloatMax)
		ExemploFloat = ExemploFloatMin;
	else if (ExemploFloat <= ExemploFloatMax)
		ExemploFloat = ExemploFloat + ExemploFloatStep;
	AddFloat(button6, "Float Example", ExemploFloat, -1, 300);
}
```
 

<strong>How to add StringArray Options</strong><br />
```C#
AddStringArray(button7, "Array Example", ExemploArray, ArrayPos, -1, 360); 
```

 
<em><strong>How to change ArrayStrign values:</strong></em><br />
```C#
string[] ExemploArray = new string[3] { "Value 1", "Value 2", "Value 3" };
public static int ArrayPos = 0;
public static int ArrayPosMax = 2;
public static int ArrayPosMin = 0;
//Loop this above<br />
if (GUI.Clicou_Button_7)
{
	GUI.Clicou_Button_7 = false;
	if (ArrayPos >= ArrayPosMax)
		ArrayPos = ArrayPosMin;
	else if (ArrayPos <= ArrayPosMax)
		ArrayPos++;
	AddStringArray(button7, "Array Example", ExemploArray, ArrayPos, -1, 360);
}
```

<hr />
 
<strong>Call colorPicker:</strong><br />

```C#
//You need loop this 
if (GUI.Clicou_Button_4)//Define your button ID 
{ 
	GUI.Clicou_Button_4 = false; //Desactive ID bool 
	ColorDialog cores = new ColorDialog(); // Call ColorDialog
		if (cores.ShowDialog() == DialogResult.OK) 
			//Function if OK pressed 
} 
```
 
<em><strong>Call colorPicker example (change top color)</strong></em><br />
```C#
//You need loop this<br />
if (GUI.Clicou_Button_3)
{
	GUI.Clicou_Button_3 = false;
        ColorDialog COLOR = new ColorDialog();
        	if (Cores.ShowDialog() == DialogResult.OK)
                {
                    AddTitle(button1, "Menu Base", -1, -1, 302, 60,
                        Cores.Color.R, Cores.Color.G, Cores.Color.B);
	}
}
```

<hr />
 
<strong>How to call MessageBox:</strong><br />
```C#
if (GUI.Clicou_Button_2)
{
	GUI.Clicou_Button_2 = false;
	MessageBox.Show("Clickkkkk");
}
 ```
</p>

<p></p>
