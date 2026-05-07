```R
library(tidyverse)
library(plotly)
library(htmlwidgets)

plot_math_scores <- ggplot(bigclass, aes(x = Math)) +
  geom_histogram(binwidth = 50, fill = '#0072B2', color = 'white', alpha = 0.8) +
  labs(title = 'Distribution of Math Scores', x = 'Math Scores', y = 'Frequency') +
  theme_minimal() +
  theme(
    plot.title = element_text(size = 20, hjust = 0.5),
    axis.title.x = element_text(size = 18),
    axis.title.y = element_text(size = 18),
    axis.text.x = element_text(size = 14),
    axis.text.y = element_text(size = 14),
    panel.background = element_rect(fill = 'white', color = NA),
    plot.background = element_rect(fill = 'white', color = NA)
  )

plotly_math_scores <- ggplotly(plot_math_scores)

output_html_path <- "/content/project/media/plots/math_scores_histogram.html"
saveWidget(plotly_math_scores, file = output_html_path, selfcontained = TRUE)
```
