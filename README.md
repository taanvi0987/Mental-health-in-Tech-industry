import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns

# Load the CSV file
df = pd.read_csv('../data/survey_results.csv')

# Display first few rows
print(df.head())

# ---------------------------
# Basic Analysis
# ---------------------------

# Age group distribution
plt.figure(figsize=(8, 5))
df['What is your age group?'].value_counts().plot(kind='bar', color='skyblue')
plt.title('Age Group Distribution of Respondents')
plt.xlabel('Age Group')
plt.ylabel('Count')
plt.tight_layout()
plt.savefig('../images/age_distribution.png')
plt.show()

# Diagnosed mental health condition
plt.figure(figsize=(6, 4))
df['Do you have a diagnosed mental health condition?'].value_counts().plot.pie(autopct='%1.1f%%', colors=['lightgreen', 'lightcoral'])
plt.title('Mental Health Condition Diagnosed')
plt.ylabel('')
plt.tight_layout()
plt.savefig('../images/diagnosed_pie.png')
plt.show()

# Comfort discussing mental health at work
plt.figure(figsize=(8, 5))
sns.countplot(data=df, x='Rate your comfort in discussing mental health at work (1-5)', palette='coolwarm')
plt.title('Comfort Level in Discussing Mental Health at Work')
plt.xlabel('Comfort Rating (1=Low, 5=High)')
plt.ylabel('Number of Respondents')
plt.tight_layout()
plt.savefig('../images/comfort_rating.png')
plt.show()

# Awareness of company policy
plt.figure(figsize=(6, 4))
df['Are you aware of your company’s mental health policy?'].value_counts().plot(kind='bar', color='orange')
plt.title('Awareness of Mental Health Policy')
plt.xlabel('Response')
plt.ylabel('Count')
plt.tight_layout()
plt.savefig('../images/policy_awareness.png')
plt.show()
# Mental-health-in-Tech-industry
