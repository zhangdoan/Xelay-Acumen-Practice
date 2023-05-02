# Xelay-Acumen-Practice
The practical demonstration for the Business analyst, Consulting Position at Xelay Acumen
library(lubridate)

Admin$Admin_Date <- ymd(Admin$Admin_Date)

# Extract the year and month from the Admin_date column
Admin$Year <- year(Admin$Admin_Date)
Admin$Month <- month(Admin$Admin_Date)

# Group the data by medication, year, and month, then summarize the total units
summary <- Admin %>%
  group_by(Med, Year, Month) %>%
  summarise(Total_Units = sum(Units, na.rm = TRUE))

# Display the summary data frame
print(summary)
