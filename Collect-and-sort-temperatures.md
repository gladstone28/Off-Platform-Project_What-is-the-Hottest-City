

Collect and Sort Temperatures
Inside our script sortCityTemps.sh:

Create an array of cities you will be getting the temperatures of. You can create an array in Bash using the format
cities=("City1" "City2" "City3")

Replace the values in the quotes with at least 3 of your favorite cities. For simplicity, let’s pick cities that don’t contain spaces in their names.

In the script, create an empty file called temperatures.txt where you will be saving the temperatures. You can use output redirection > to accomplish this.

For example, the command > movies.log will create an empty file called movies.log. If this file already exists, the command will overwrite it. This makes sure there’s a fresh, blank version of this file each time the script is run.

Next, you need to set up a loop to iterate through the cities in the array you created. Using a for loop makes this an easy task:

for city in ${cities[@]}
do
# commands to repeat
done

The city variable takes the value of item inside the array on each iteration of the loop. On the first iteration, for example, it will be assigned to “City1”. “City2” on the second iteration. “City3” on the third iteration and so on. 4. Inside the loop, add the command sleep 1. This pauses the script for 1 second at every iteration to ensure you do not send too many requests to the API in a short amount of time. 5. Inside the loop, call our modified script weather.sh using the city variable as the parameter. Make sure to use the -s option to get the simplified weather output.

We encourage you to run the script in-between steps for the sake of testing. Before continuing to the next step, try printing out the output from the weather.sh script using echo. Remember the simplified output looks like Paris +39°F. 6. You need to remove the extra symbols like + and °F so the data is easily sortable. Pipe the output of the weather script into the sed command to replace these with an empty string. For example, sed 's/+//' removes the + symbol from the output.

You may need to pipe and use the sed command more than once. 7. Using output redirection >>, append the final weather output to a file called temperatures.txt (in the first iteration, since the file doesn’t exist yet, it will be automatically created. In the iterations after that, the temperatures will be appended).

After running the script at this point, temperatures.txt should contain something like this:

Paris 46
Tokyo 64
London 36

Finally, let’s sort the temperatures saved in the temperatures.txt file in descending order and save that sorted output to a final file.

In the script after the loop, use the sort command on the file containing our city temperatures. The sort command by default will sort according to the city name in ascending order. But you want it to sort according to the temperatures in descending order! Use sort on temperatures.tx with the options -k2 (to sort based on the second value in each line) and -r to sort in descending order.
Save the sorted output to a file called sorted_temperatures.txt using output redirection >.
Save and run./sortCityTemps.sh. Open the file sorted_temperatures.txt and see that the cities are now sorted according to their current temperatures.

link to the informational page

https://www.codecademy.com/courses/introduction-to-linux-bash-scripting/articles/whats-the-hottest-city-bash-off-platform


