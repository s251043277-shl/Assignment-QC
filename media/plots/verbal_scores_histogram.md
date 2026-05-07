```R
library(tidyverse)
library(plotly)
library(htmlwidgets)

plot_verbal_scores <- ggplot(bigclass, aes(x = Verbal)) +
  geom_histogram(binwidth = 50, fill = '#D55E00', color = 'white', alpha = 0.8) +
  labs(title = 'Distribution of Verbal Scores', x = 'Verbal Scores', y = 'Frequency') +
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

plotly_verbal_scores <- ggplotly(plot_verbal_scores)

output_html_path_verbal <- "/content/project/media/plots/verbal_scores_histogram.html"
saveWidget(plotly_verbal_scores, file = output_html_path_verbal, selfcontained = TRUE)
```
