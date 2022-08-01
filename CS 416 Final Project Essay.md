## CS 416 Final Project Essay

- Jiayuan Li (jiayuan8@illinois.edu)

### Messaging

The project uses the [fuel effeciency dataset](https://flunky.github.io/cars2017.csv) provided in course for narrative visualization. The general idea of the project is to visualize the relationship between number of engine cylinders  and fuel efficiency of cars. The main message is that cars with more engine cylinders has worse fuel efficiency in multiple metrics than cars with less engine cylinders. (or electrical cars which have 0 cylinders)

### Narrative Structure

The project uses interactive slide show, where the viewer can switch between the 3 scenes by using the switch button at top of the web page. In each scene, viewers can view and interact with the chart. 

### Visual Structure

Each scene includes a horizontal bar chart. The x-axis represent fuel efficiency metrics, including `Average Highway MPG` and `Average City MPG`. The y-axis represent number of engine cylinders/car manufacturer. The title of each scene are displayed at the top of each page. The scene-switch buttons are positioned below the title so the users can easily spot and user them to switch between different scenes. The current scene are also displayed which can facilitate user understand where they are in the narrative visualization. To ensure the viewers to focus on the important parts, the bar chart uses light blue colors to attract views' attention. The entries are also displayed in a sorted way to let user find the trend of the dataset easily. Detailed number such as the actual `Car Count` for each number of engine cylindars are hiddin unless user place the mouse on the bar chart. To help viewer trasition between different scenes and understand data in different scene, we always have the x-axis as the fuel efficiency metrics so they can get used to the new information easily. 

### Scenes

There are three scenes in the visualization. The first scene is `Number of Engine Cylinders v.s. Average City MPG `. The second scene is `Number of Engine Cylinders v.s. Average Highway MPG`. These two scenes gives viewer a general concept of how do fuel efficieny and number of engine cylinders related and views can realize the relationship that as number of engine cylinder increases, the fuel efficiency decreases. The third scene is about different car manufacturers v.s. averaged `Average City MPG` level. Then brand are sorted by average engine cylinders of cars in each brand. Hence, user can identify that although the bar charts has some fluctuation, the negative relationship of number of engine cylinders and fuel effiency still maintains. 

### Annotations

The annotations are used to mark special entries (such as electrical cars, with 0 cylinders), small sample entries (average value calculated by only one value) and general trend (negative relationship between two variables). For special entries and general trend, the default template of annotations in `d3` are used. For small sample entries, the callout circle template in `d3` is used. The idea of using different template is to distinguish the different types of message, such as general trend v.s. outliers. So that viewers can easily figure out that the annotations are conveying different type of message. 

### Parameters

The parameter mainly used are two list. The first list is a list of dict and for each entry there is a dictionary of `EngineCylinders`, `AverageCityMPG`, `AverageHighwayMPG`,  and `CarCount`. The parameter is calculated by passing the raw `d3` data object to `calculateCylinderStat` method and it is mainly used for scene 1 and 2. The second list is also a list of dict and for each entry there is a dictionary of `Make`, `AverageCityMPG`, `AverageEngineCylinders`, `CarCount`. The parameter is calculated by passing the raw `d3` data object to `calculateBrandState` method and it is mainly used for scene 3. The states are defined by number 1, 2 and 3. Each scene are defined in a separate div with a separate `loadSceneX` function. When user click on the switch scene button, the corresponding `loadSceneX` function will be called which will hide the other scenes and display the chosen scene. 

### Triggers

When user hover on the bar chart, more detailed information about the data entry will show up. When user stop hover on the bar chart, the displayed message will disapper. The area of the rectangles in the bar chart are made large to attract user to futher investigate on it. 