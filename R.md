- 👋 Hi, I’m @NeddyD
- 👀 I’m interested in ... scifi movie and mobile app
- 🌱 I’m currently learning ... JavaScript
- 💞️ I’m looking to collaborate on ...
- 📫 How to reach me ...

<!---
NeddyD/NeddyD is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
---> 
**#R_melt_dual axis line plot**
o3_h <- melt(o3_h, id.vars = "date", variable.name = "pollutant", value.name = "value")
> ggplot(no2_h, aes(x = date, y = value, color = pollutant)) +
    geom_line(size = 0.8) + scale_color_manual(values = c("blue", "red")) +
    facet_wrap(~ pollutant, scales = "free_y", ncol = 1, strip.position = "right") +
    labs(x = "Date", y = NULL, color = "Pollutant") +
    theme_bw() +
    theme(legend.position = "none")

**#best aesthetic scatter plot with regression with my xlsx data in R**
ggplot(hourly, aes(x = NO2_ground, y = NO2_pandora)) +
     geom_point(color = "#36454F", size = 3, alpha = 1) +     
     geom_smooth(method = "lm", color = "#FF0000", se = TRUE) +  
     theme_bw() +                                           
     labs(title = "Hourly average concentration of Nitrogen dioxide (NO2)",  
          x = "NO2 concentration [ug/m3] atn UB3 station",
          y = "NO2 total vertical column amount [mol/m2]") +
     theme(plot.title = element_text(hjust = 0.5, face = "bold"),
           text = element_text(size = 12))   

# To show the regression equation in the format y=mh+c R2 value on the scatter plot 
model <- lm(no2p ~ no2g, data = hourly)

intercept <- round(coef(model)[1], 2)
slope <- round(coef(model)[2], 2)
r_squared <- round(summary(model)$r.squared, 2)
p_value <- summary(model)$coefficients[2, 4]

# Create equation and R-squared label
equation <- paste("y = ", slope, "*x + ", intercept, "\nR² = ", r_squared, sep = "")
equation <- paste("y = ", slope, "*x + ", intercept, "\nR² = ", r_squared, "\np = ", round(p_value, 3), sep = "")

**#last**
ggplot(hourly, aes(x = no2g, y = no2p)) +
    geom_point(color = "#36454F", size = 3, alpha = 1) +   
    geom_smooth(method = "lm", color = "#FF0000", se = TRUE) +   
    theme_bw() +      
    labs(title = "Hourly average concentration of Nitrogen dioxide (NO2)",  
         x = "NO2 concentration [ug/m3]",
         y = "NO2 total vertical column amount [mol/m2]") +
    theme(plot.title = element_text(hjust = 0.5, face = "bold"), 
          text = element_text(size = 12)) + xlim(0,300) + ylim(0,0.0008) + 
    annotate("text", x = Inf, y = Inf, label = equation,   
             hjust = 1.1, vjust = 1.5, size = 5, color = "black") 

**#netcdf data era5 single layer data (boundary layer) UB**
library(ncdf4)    # For reading NetCDF files
library(raster)   # For raster operations
library(ggplot2)  # For plotting
library(dplyr)    # For data manipulation
library(tidyr)    # For reshaping data
nc_data <- nc_open("C:/Users/DELL/Documents/ub air quality data/boundary_layer/raw_data/2023_2024.nc")
print(nc_data)
