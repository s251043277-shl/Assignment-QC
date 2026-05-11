```R
# Create the violin plot for age distribution by sex
plot_obj <- ggplot(bigclass, aes(x = sex, y = age, fill = sex)) +
  geom_violin(trim = FALSE, alpha = 0.7) +
  geom_boxplot(width = 0.1, outlier.shape = NA, fill = "white") +
  labs(
    title = "Age Distribution by Sex in Bigclass Dataset",
    x = "Sex",
    y = "Age"
  ) +
  theme_minimal() +
  theme(axis.title.x = element_text(size = 18),
        axis.title.y = element_text(size = 18),
        axis.text = element_text(size = 14),
        panel.background = element_rect(fill = "white", colour = "white")) +
  scale_fill_manual(values = c("F" = "#D55E00", "M" = "#0072B2"))

# Convert to plotly object and save as HTML
plotly_obj <- ggplotly(plot_obj)
saveWidget(plotly_obj, "media/plots/age_distribution_violin.html", selfcontained = TRUE)
```
