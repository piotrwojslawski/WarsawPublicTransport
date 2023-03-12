# WarsawPublicTransport

This project aims to gather precise arrival timings for both buses and trams at every stop located in Warsaw and compute the delays for buses. The project is divided into two scripts:

# 1. Timetable script.ipynb
The primary objective of this script is to gather accurate arrival time data. It collects information about all the stops in Warsaw through the API access point (https://api.um.warszawa.pl/).\
In the first stage, the script collects data of all stops in Warsaw. This data includes stop number (zespol), stop label (slupek), longitude (dlug_geo), and latitude (szer_geo).\
At the second stage, the script sends a request to the API for each stop number, stop label, and line number to collect accurate arrival time data. Using this information, it generates a timetable DataFrame, which includes fleet number (brygada), time (czas), stop name (stop_name), stop number (stop_id), stop label (bus_stop_nr), line number (line), longitude (Lon), and latitude (Lat). Finally, it saves this DataFrame as a timetable.csv file, which is available in the repository.

    ![image](https://user-images.githubusercontent.com/55345644/224541086-0630a9d2-3eec-4061-bbfa-5a6353f8f98f.png)


# 2. Delays script.ipynb
The objective of this script is to compute bus delays in Warsaw. The delays are determined by analyzing data from two sources:\
- timetable.csv file, which was generated by the previous script and provides information about where a particular bus should be at a specific time
- API requests that provide real-time information about the current location of the buses.\
Using timetable.csv file and real-time data on the current location of buses, the script calculates the delay in minutes for each bus. The delay is determined by comparing the expected arrival time of a bus at a particular stop, as provided by the timetable.csv file, with the actual arrival time of the bus at that stop, as obtained from the real-time data.\
Finally, the script generates a DataFrame that includes fleet number (brygada), line number (line), expected arrival time (arrival_time), current location (current_location), delay (delay), and timestamp (timestamp).

    ![image](https://user-images.githubusercontent.com/55345644/224541023-4bddd3e0-edee-4863-b4c3-ae4fde88243f.png)

Final information displayed on the chart.

    ![image](https://user-images.githubusercontent.com/55345644/224541108-19d4d4d1-f924-460c-bead-fd3869e6efb3.png)



