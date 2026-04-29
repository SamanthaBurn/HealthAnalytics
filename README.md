# Introduction to Health Analytics

Course materials for "Introduction to Health Analytics", a course developed by Samantha Burn and offered at Imperial Business School.

## About the Course

This course covers introductory topics in health analytics including:

- Data wrangling and manipulation with dplyr and tidyverse
- Data visualization with ggplot2
- Causal inference methods
- Linear regression and hypothesis testing
- Fixed effects and difference-in-differences estimators
- Limited dependent variable models
- Machine learning for health applications

## Course Website

Visit the course website for rendered lectures, exercises, and tutorials:
[Introduction to Health Analytics](https://example.com/health-analytics) *(placeholder URL)*

## Repository Contents

- **lectures/**: Quarto slides for the 10 course lectures
- **exercises/**: R Markdown exercise sets with solutions for hands-on practice
- **tutorials/**: Step-by-step tutorials covering key workflows and methods
- **practice_exam/**: Additional practice materials and exam preparation resources
- **data/**: Sample datasets used throughout the course

## Technology

This course uses:

- **R** (https://www.r-project.org/)
- **RStudio** (https://posit.co/download/rstudio-desktop/) — Integrated development environment for R
- **Quarto** (https://quarto.org/) — Publishing system for dynamic documents combining code and text

## Getting Started

### Prerequisites

- R 4.0 or later
- RStudio
- Git (to clone the repository)

### Installation

1. **Clone the repository:**
   ```bash
   git clone https://github.com/yourusername/HealthAnalytics-public.git
   cd HealthAnalytics-public
   ```

2. **Install R and RStudio:**
   - Download R: https://www.r-project.org/
   - Download RStudio: https://posit.co/download/rstudio-desktop/

3. **Open the project in RStudio:**
   - Open `exercises/exercises.Rproj` in RStudio, or
   - Open any individual `.Rmd` or `.qmd` file

4. **Install required R packages:**
   ```r
   install.packages(c("tidyverse", "ggplot2", "dplyr", "rmarkdown", "quarto"))
   ```

### Using the Materials

- **Lectures**: View the rendered HTML slides on the course website or render with Quarto (`quarto render lectures/`)
- **Exercises**: Open `.Rmd` files in RStudio and work through the problems
- **Tutorials**: Start with `tutorials/01_dataviz/` and progress through each folder
- **Solutions**: Check solutions files after attempting exercises yourself

## Course Structure

The course progresses from foundational R skills to advanced statistical methods:

1. Introduction to Health Data & R
2. Data Visualization
3. Data Wrangling
4. Causal Inference
5. Linear Regression
6. Hypothesis Testing
7. Fixed Effects & Difference-in-Differences
8. Limited Dependent Variables
9. Machine Learning
10. Course Review

## Learning Objectives

By completing this course, students will be able to:

- Import, explore, and visualize health data using R
- Clean and wrangle messy datasets for analysis
- Understand and apply causal inference methods
- Build and interpret regression models
- Conduct hypothesis tests and understand statistical inference
- Apply advanced econometric methods like difference-in-differences
- Build and evaluate machine learning models for health applications
- Produce reproducible research using R and Quarto

## Acknowledgements

Many thanks to the following people for sharing materials: Sam Asher, Scott Cunningham, Alex
Hoagland, Nick Huntington-Klein, Laura Lufray, Fintan Nagle, Simon Quinn, Nicola Rennie, 
and Shuang Zhang.

## Contributing

These are course materials. For suggestions, improvements, or corrections, please open an issue or submit a pull request.

## License

These materials are provided for educational purposes. Please see the LICENSE file for specific licensing information.

## Contact & Support

For questions about the course content or materials, refer to the course website or contact the instructor.

---

**Last Updated:** April 2026

**Built with:** Quarto, R, and RStudio
