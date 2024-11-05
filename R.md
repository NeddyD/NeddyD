- 👋 Hi, I’m @NeddyD
- 👀 I’m interested in ... scifi movie and mobile app
- 🌱 I’m currently learning ... JavaScript
- 💞️ I’m looking to collaborate on ...
- 📫 How to reach me ...

<!---
NeddyD/NeddyD is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
---> #R_melt_dual axis line plot
o3_h<- melt(o3_h, id.vars = "date", variable.name = "pollutant", value.name = "value")
> ggplot(no2_h, aes(x = date, y = value, color = pollutant)) +
    geom_line(size = 0.8) + scale_color_manual(values = c("blue", "red")) +
    facet_wrap(~ pollutant, scales = "free_y", ncol = 1, strip.position = "right") +
    labs(x = "Date", y = NULL, color = "Pollutant") +
    theme_bw() +
    theme(legend.position = "none")
