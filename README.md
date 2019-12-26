# Toggle-Switch-CSS
Pure CSS no use of framework.

Let’s create an input checkbox with label, so that we can change the label as switch and turn on the switch when the checkbox is checked and turn off when it is unchecked.

> <input type="checkbox" id="toggle" class="checkbox" />
> <label for="toggle" class="switch"></label>

The label is placed below the input so that we can select the label using the adjacent selector(+) .

Now the checkbox is created.

Now we need to change the label position as relative , so that we can make use of `label::after` and style that to appear like a switch. Also set the `display : inline-block;` so that we can apply width and height for the label.

> .switch {    
> position : relative ;   
> display : inline-block;   
> width : 40px;
> height : 20px;   
> background-color: #eee;   
> border-radius: 20px; }

Now the toggle switch looks like ,

Let’s add the circle ⭕️ to the toggle switch using `::after` pseudo class.

>  .switch::after {  
>  content: '';  
>  position: absolute;  
>  width: 18px;  
>  height: 18px;  
>  border-radius: 50%;  
>  background-color: white;  
>  top: 1px; // TO GIVE AN EFFECT OF CIRCLE INSIDE SWITCH.  
>  left: 1px;  transition: all 0.3s;}

Now the switch looks like

Now we need to change the background color and position of circle when the checkbox is selected , for that let’s use `:checked` property on input. if the input box is checked then change the background color of label and change the position of the circle.

> .checkbox:checked + .switch::after {  
> left : 20px; }
> .checkbox:checked + .switch {  
> background-color: #7983ff;}

Now when the checkbox is checked the input looks like
Final output.

Let’s hide the checkbox

> .checkbox { 
> display : none;}
