
library(devtools)  
#devtools::install_github("Mattciao96/ritalic", force = TRUE)
library(ritalic)

# activate other utility libraries
library(dplyr)

dataset <- read.csv("dataset-test.csv")

dataset_names <- dataset$sp

# align names to the checklist of italic
aligned_names <- ritalic::italic_match(dataset_names)

names_to_keep <- aligned_names %>% 
  filter(name_score == 100)


accepted_names_list_unique <- unique(names_to_keep$accepted_name)

# we can look at the taxonomic classification
taxonomic_class <- ritalic::italic_classification(accepted_names_list_unique)
# fix na

# we can look at taxon data
taxon_data <- ritalic::italic_taxon_data(accepted_names_list)

# we can look at functional traits
traits <- italic_traits(accepted_names_list_unique)
traits2 <- italic_traits(accepted_names_list)

listona <- italic_checklist()
traits_all <- italic_traits(listona)

write.csv(traits, 'taxon_traits.csv', row.names = F, na = '')


