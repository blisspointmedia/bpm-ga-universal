# bpm-ga-classic
Bliss Point Media GA Universal Lower funnel metrics example

In order to carry a timestamp from a higher-funnel action into a lower-funnel action, we use a cookie to save and retrieve it when needed. When the lower-funnel action that we want to measure occurs, we send an event with the category name 'BpmSessionStartDelta', along with a delta (in millis) to the start of the session.

To set up the custom dimension, do the following:
1. Sign in to Google Analytics.
2. Select the Admin tab and navigate to the property to which you want to add custom dimensions.
3. In the PROPERTY column, click Custom Definitions, then click Custom Dimensions.
4. Click New Custom Dimension.
5. Add a Name="BpmSessionStartDelta".
6. Select the Scope=”Hit”
7. Check the Active box to start collecting data and see the dimension in your reports right away. To create the dimension but have it remain inactive, uncheck the box.
8. Click Create.
9. Note the index of the custom dimension

To retrieve this information, make a custom query as follows:
	Dimensions: Date, Hour, Minute, BpmSessionStartDelta
	Metrics: New Users (or whatever you want)

The Date/Hour/Minute in the report signify the timestamp of the lower-funnel event. Then by subtracting the milliseconds specified by BpmSessionStartDelta, we can retrieve the session start time.
