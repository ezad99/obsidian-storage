2024-10-16 10:43

Status:

Tags:

# FYP Development Plan
### 1. **Define Core Features for the MVP**

To keep things simple yet effective, consider the following core features for your platform:

1. **Interactive Java Exercises**:
    
    - Users can complete coding exercises in Java, where they write code to solve specific problems.
2. **AI-Powered Feedback**:
    
    - Integrate an LLM to provide real-time feedback on users’ code submissions, offering suggestions for improvements or debugging assistance.
3. **Progress Tracking**:
    
    - Basic user accounts that allow tracking of exercises completed and feedback received.
4. **Simple User Interface**:
    
    - A clean and intuitive UI to keep users engaged and focused on learning.

### 2. **Technology Stack**

Given the timeframe and your focus on ease of development, here’s a suggested tech stack:

- **Frontend**:
    
    - Use **HTML/CSS/JavaScript** with a simple framework like **React** or **Vue.js**. If you want to keep it even simpler, plain HTML/CSS with some JS can work.
- **Backend**:
    
    - **Django**: Choose Django for its rapid development capabilities and ease of use. You can also leverage Django Rest Framework to build APIs.
    - **OpenAI API**: Use the OpenAI API for the language model to provide feedback on code submissions.
- **Database**:
    
    - Use **SQLite** for simplicity, as it's easy to set up and requires no configuration.

### 3. **Development Plan**

Here’s a **10-week development plan**, broken down by weeks and tasks:

#### **Weeks 1-2: Setup and Basic Functionality**

- **Week 1**:
    
    - **Setup Environment**: Install Django and create a new project.
    - **Basic Structure**: Set up the basic structure of your Django app (models, views, and URLs).
    - **Create User Accounts**: Implement basic user registration and authentication using Django's built-in authentication.
- **Week 2**:
    
    - **Develop Exercise Model**: Create a simple model for coding exercises (title, description, input/output).
    - **Create Exercise Pages**: Develop a frontend to display exercises to users.

#### **Weeks 3-4: Integrating AI Feedback**

- **Week 3**:
    
    - **Integrate OpenAI API**: Set up the OpenAI API to accept code submissions and return feedback.
    - **Basic AI Functionality**: Create a basic function to send user code to the API and retrieve feedback.
- **Week 4**:
    
    - **User Interface for Code Submission**: Build a simple form where users can submit their code for an exercise.
    - **Display AI Feedback**: Show the feedback from the AI on the webpage after submission.

#### **Weeks 5-6: Adding Exercises and Progress Tracking**

- **Week 5**:
    
    - **Add Sample Exercises**: Populate the database with a few sample Java exercises.
    - **Test Exercise Flow**: Ensure users can select exercises and submit code for feedback.
- **Week 6**:
    
    - **Implement Progress Tracking**: Develop functionality to track completed exercises for each user.
    - **Basic Dashboard**: Create a simple user dashboard to display their progress.

#### **Weeks 7-8: UI Improvements and Testing**

- **Week 7**:
    
    - **UI Enhancements**: Improve the user interface to make it more engaging and user-friendly.
    - **Responsive Design**: Ensure the platform works well on different devices (use CSS frameworks like Bootstrap or Tailwind CSS for quicker styling).
- **Week 8**:
    
    - **Testing**: Test the platform thoroughly. Ensure that user authentication, exercise submissions, and AI feedback are working smoothly.
    - **Collect Feedback**: If possible, have a few users test the platform and provide feedback.

#### **Weeks 9-10: Final Touches and Deployment**

- **Week 9**:
    
    - **Implement Final Features**: Add any last-minute features based on feedback (e.g., error handling, additional exercises).
    - **Documentation**: Write basic documentation for users on how to use the platform.
- **Week 10**:
    
    - **Deployment**: Deploy your application using platforms like Heroku or PythonAnywhere. These platforms support Django applications and are relatively straightforward to set up.
    - **Launch MVP**: Share your platform with users to gather feedback and start iterating on improvements.

### 4. **Tips for Success**

- **Focus on Simplicity**: Don’t aim for a perfect product. Prioritize getting a working MVP out quickly, and iterate based on user feedback.
- **Use Existing Libraries**: Leverage libraries for user authentication and other common features instead of building everything from scratch.
- **Stay Organized**: Use project management tools like Trello or Notion to track your progress and tasks.
- **Ask for Help**: Utilize online communities (like Stack Overflow or Reddit) if you run into issues; they can be invaluable for quick solutions.


# References

