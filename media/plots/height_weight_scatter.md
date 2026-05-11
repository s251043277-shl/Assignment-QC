```R
# Create the scatter plot
plot_obj <- ggplot(bigclass, aes(x = height, y = weight, color = sex)) +
  geom_point(alpha = 0.7) +
  labs(
    title = "Height vs. Weight in Bigclass Dataset",
    x = "Height (inches)",
    y = "Weight (pounds)"
  ) +
  theme_minimal() +
  theme(axis.title.x = element_text(size = 18),
        axis.title.y = element_text(size = 18),
        axis.text = element_text(size = 14),
        panel.background = element_rect(fill = "white", colour = "white"))

# Convert to plotly object and save as HTML
plotly_obj <- ggplotly(plot_obj)
saveWidget(plotly_obj, "media/plots/height_weight_scatter.html", selfcontained = TRUE)
```
