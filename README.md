import time
import random

# Simulate a database table with sample data
database = {
    'user_id': [i for i in range(1, 10001)],
    'username': [f'user{i}' for i in range(1, 10001)],
    'score': [random.randint(1, 1000) for _ in range(10000)]
}

# Function to perform a sample query on the database
def query_database(user_id):
    for i in range(len(database['user_id'])):
        if database['user_id'][i] == user_id:
            return database['score'][i]
    return None

# Measure the time taken to perform the query
start_time = time.time()
user_score = query_database(5000)
end_time = time.time()

# Display the result and time taken
if user_score is not None:
    print(f"User score: {user_score}")
    print(f"Time taken: {end_time - start_time} seconds")
else:
    print("User not found")

