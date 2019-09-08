       

Course  Bringing Data To Life With Visualizations  DC.js and Crossfilter.js  Composite Charts 
 



 


video 
Composite Charts
 
#Composite Charts 
 
## 
What is it?
A composite chart 
 
##What does it do?
It is a chart of the relationship between the groups within a dimension 
 
##How do you use it?
Use a composite chart to view and compare groupings within a dimension. 
Walkthrough

 



0:03 / 9:41
Press UP to enter the speed menu then use the UP and DOWN arrow keys to navigate the different speeds, then press ENTER to change to the selected speed.
2.0x
Click on this button to mute or unmute this video or press UP or DOWN buttons to increase or decrease volume level.
Maximum Volume.
HD
High Definition
 
on
Video transcript
Start of transcript. Skip to the end.
In our last example, we tracked the total spend over a particular time period, actually, over the entire time period available to us from our dataset.
But what if we wanted to view Tom's spend over that time period, or Alice's spend, or Bob's spend over that time period?
One way of doing it would be to create an individual graph for each.
But a more efficient way of doing that could be to create a composite graph, or a composite chart, where we can see Bob's, Alice's, and Tom's spend all in the same chart.
And we can easily make a visual comparison between the spends.
So let's do that now.
We have the basics of our functions in place; that's often called boilerplate in software development.
So we have our makeGraphs() function in place. We have our Queue() with our imports.
We have already parsed the data. Copy and paste the formatting functionality.
And let's get our date dimension.
Group it and reduce to the spend.
In this case, we're going to do a check.
We're going to say if (d.name === 'Tom') then we're going to return +d.spend.
That's the spend instance for Tom.
And you might notice there the + in front of the d.
Well, that's a JavaScript shortcut, or little trick, that attempts to convert a number that's been represented in string format into an actual number.
So that's Tom spend by month.
It's a way of cleaning up the data, as well. It's a way of avoiding dirty data.
So if we can't convert the spend string to an integer, we return 0 instead.
And it allows us to render our charts more easily.
So we have Tom, Bob, and Alice.
So we have tomSpendByMonth, bobSpendByMonth, and aliceSpendByMonth.
Then we create our compositeChart.
Once we have created the compositeChart object, we then begin the process of chaining our functions, so we can provide attribute values.
So we give it a height and a width.
Height of 990 and width of 200.
And our dimension.
That's the data dimension that we're going to work with.
Again, we're going to use a time scale, as opposed to a linear scale or an ordinal scale.
And we use our minDate and maxDate to provide our domain.
Give our y-axis a label, and we'll call it 'Spend'.
We're introducing a legend here as well.
And we add our positioning of the legend. Remember that's the positioning relative to the chart itself within the viewport.
There's a gap of five units.
There will be a color-coded legend for Tom, Bob, and Alice.
And we're also rendering our horizontal gridlines, again, to provide more visual cues when comparing and contrasting.
Then we invoke the compose() function.
And inside there, we create a line chart.
So we then group.
And we repeat, so we create one for Tom, we create a line chart for Bob, and we will create a line chart for Alice.
We set the brushOn(false).
Remember in the last unit, we mentioned that the brush is on by default .
You can specify brushOn to be false.
Remember to call renderAll.
Unless you call renderAll, the chart won't render. It won't display on your browser.
There you go. That's pretty nice.
Again, it's interactive. You can click on the legend.
Those individual spends will be highlighted.
So let's refactor a little bit.
You can see that where we have tomSpendByMonth, bobSpendByMonth, and aliceSpendByMonth, the code looks almost identical, except for the string name that we're matching.
So we can be a bit more clever about it, more efficient, or what I call lazy.
Good programmers are lazy programmers.
And when I say lazy, I mean efficient.
Why reinvent the wheel, why repeat yourself?
If you have the opportunity to create a piece of code once and just pass different parameter values, then that's more efficient.
It reduces file size as well.
We created a function called spend_by_name() that takes in a string. Let's call it name.
And as with all variables, name your parameters in such a way that reflects the data being passed in.
We're expecting names, so we call it name.
This allows us to reduce our file size and make our code that little bit more readable.
Okay, it still works.
There you have it: a composite chart.
End of transcript. Skip to the start.
View Source Code
 
 
 
