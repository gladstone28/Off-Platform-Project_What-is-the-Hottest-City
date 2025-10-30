

#### Project Setup

Even though the wttr.in API is highly customizable, the original weather script is not. This is why we made our own version of the weather command which can show a much simpler output such as: Paris +39°F.

#### Install Modified weather Script

Let’s begin by opening up a terminal inside VirtualBox Ubuntu Desktop and:

- Download our modified weather script using the command
wget https://static-assets.codecademy.com/Courses/learn-linux/weather-offplatform-project/weather.sh
- Give it executable permissions using the command
chmod +x weather.sh.
- See the usage of our script with ./weather.sh -h.
We retained the original functionality of the weather utility while adding an option, -s, to show a simpler output. Try out the script with and without the -s option. You could try some of the examples below:

- ./weather.sh
- ./weather.sh Tokyo
- ./weather.sh -s Tokyo

Notice the original output is quite fancy, which makes it challenging to filter out the temperature.

#### Optional: Install Bash-Snippets weather Script

Installing the original weather script from Bash-Snippets is optional. However, it is recommended if you are familiar with git and if you wish to further improve on the script you will be writing in this project.

Click here for the instructions.

To install the official weather script from Bash-Snippets. Enter the following commands one at a time on the terminal:

- $ sudo apt -y install git
- $ git clone https://github.com/alexanderepstein/Bash-Snippets
- $ cd Bash-Snippets/
- $ git checkout v1.23.0
- $ sudo ./install.sh weather

Once the weather script is installed, see its usage with weather -h and try it out!

