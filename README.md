# Create the new 'family_size' variable by adding sibsp, parch, and 1 (for the passenger themselves)
titanic['family_size'] = titanic['sibsp'] + titanic['parch'] + 1

# Display the first few rows to verify
print(titanic[['sibsp', 'parch', 'family_size']].head())

# Visualize the relationship between family_size and survived
plt.figure(figsize=(10, 6))
sns.barplot(x='family_size', y='survived', data=titanic, palette='autumn')
plt.title("Survival Rate Based on Family Size")
plt.xlabel("Total Family Size")
plt.ylabel("Survival Rate")
plt.show()
