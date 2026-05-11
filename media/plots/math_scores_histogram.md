```R
# Create the histogram for Math Scores
plot_obj <- ggplot(bigclass, aes(x = Math)) +
  geom_histogram(binwidth = 50, fill = "#0072B2", color = "white", alpha = 0.8) +
  labs(
    title = "Distribution of Math Scores in Bigclass Dataset",
    x = "Math Score",
    y = "Frequency"
  ) +
  theme_minimal() +
  theme(axis.title.x = element_text(size = 18),
        axis.title.y = element_text(size = 18),
        axis.text = element_text(size = 14),
        panel.background = element_rect(fill = "white", colour = "white"))

# Convert to plotly object and save as HTML
plotly_obj <- ggplotly(plot_obj)
saveWidget(plotly_obj, "media/plots/math_scores_histogram.html", selfcontained = TRUE)
```
