# Use an official Python runtime as a parent image
FROM python:3.9

# Set the working directory in the container
WORKDIR /app

# Copy the requirements.txt file into the container at /app
COPY requirements.txt /app/

# Install any needed packages specified in requirements.txt
RUN pip install --no-cache-dir -r requirements.txt

# Copy the current directory contents into the container at /app
COPY . /app/

# Set environment variables
ENV DJANGO_SETTINGS_MODULE=mywebapp.settings
ENV PYTHONUNBUFFERED=1

# Expose the port that the app will run on
EXPOSE 8000

# Run app.py when the container launches
CMD ["gunicorn", "myapp.wsgi:application", "--bind", "0.0.0.0:8000"]
