import { useState, useEffect } from 'react';

// Main App component which controls the entire application flow
export default function App() {
  const [view, setView] = useState('home'); // 'home', 'dashboard', 'course'
  const [currentCourse, setCurrentCourse] = useState(null);

  // A simple navigation function to change the view
  const navigateTo = (newView, course = null) => {
    setView(newView);
    setCurrentCourse(course);
  };

  // State to hold the mock course data
  const [courses, setCourses] = useState([
    {
      id: 1,
      title: 'Introduction to Calculus',
      teacher: 'AI Professor Athena',
      icon: 'https://placehold.co/48x48/0000FF/FFFFFF?text=A',
      description: 'Learn the fundamentals of derivatives and integrals.',
      subject: 'Math',
      voice: 'Kore' // Voice for TTS
    },
    {
      id: 2,
      title: 'World History: Ancient Civilizations',
      teacher: 'AI Historian Clio',
      icon: 'https://placehold.co/48x48/8B4513/FFFFFF?text=H',
      description: 'Explore the rise and fall of ancient societies.',
      subject: 'History',
      voice: 'Charon' // Voice for TTS
    },
    {
      id: 3,
      title: 'Creative Writing Basics',
      teacher: 'AI Tutor Bard',
      icon: 'https://placehold.co/48x48/B8860B/FFFFFF?text=W',
      description: 'Develop your storytelling skills and find your unique voice.',
      subject: 'English',
      voice: 'Puck' // Voice for TTS
    },
    {
      id: 4,
      title: 'Fundamentals of Physics',
      teacher: 'AI Scientist Newton',
      icon: 'https://placehold.co/48x48/FF4500/FFFFFF?text=P',
      description: 'An introduction to the laws governing the universe.',
      subject: 'Science',
      voice: 'Orus' // Voice for TTS
    }
  ]);

  // Main rendering logic based on the current view state
  return (
    <div className="min-h-screen bg-gray-50 flex items-center justify-center p-4">
      <div className="w-full max-w-4xl bg-white rounded-xl shadow-2xl p-6 md:p-10 flex flex-col items-center">
        {view === 'home' && <HomePage navigateTo={navigateTo} />}
        {view === 'dashboard' && <DashboardPage navigateTo={navigateTo} courses={courses} />}
        {view === 'course' && currentCourse && <CoursePage navigateTo={navigateTo} course={currentCourse} />}
      </div>
    </div>
  );
}

// Home/Landing Page Component
function HomePage({ navigateTo }) {
  return (
    <div className="text-center p-4">
      <h1 className="text-4xl md:text-5xl font-bold text-gray-800 mb-4">
        Welcome to School.lasavo.org
      </h1>
      <p className="text-lg md:text-xl text-gray-600 mb-8">
        Learn anything from anywhere with our world-class AI teachers.
      </p>
      <button
        onClick={() => navigateTo('dashboard')}
        className="px-8 py-3 bg-indigo-600 text-white font-semibold rounded-lg shadow-md hover:bg-indigo-700 transition-colors duration-300"
      >
        Start Your Learning Journey
      </button>
    </div>
  );
}

// Dashboard Page Component
function DashboardPage({ navigateTo, courses }) {
  return (
    <div className="w-full">
      <h2 className="text-3xl font-bold text-gray-800 mb-6">Your Dashboard</h2>
      <div className="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-6">
        {courses.map(course => (
          <CourseCard key={course.id} course={course} navigateTo={navigateTo} />
        ))}
      </div>
      <button
        onClick={() => navigateTo('home')}
        className="mt-8 px-4 py-2 text-sm bg-gray-200 text-gray-800 rounded-lg shadow-sm hover:bg-gray-300 transition-colors duration-300"
      >
        Back to Home
      </button>
    </div>
  );
}

// Course Card Component
function CourseCard({ course, navigateTo }) {
  return (
    <div className="bg-white rounded-lg shadow-lg p-6 border border-gray-200 hover:shadow-xl transition-shadow duration-300">
      <div className="flex items-center mb-4">
        <img src={course.icon} alt={`${course.teacher} icon`} className="w-12 h-12 rounded-full mr-4" />
        <div>
          <h3 className="text-xl font-semibold text-gray-800">{course.title}</h3>
          <p className="text-sm text-gray-500">Taught by {course.teacher}</p>
        </div>
      </div>
      <p className="text-gray-600 mb-4">{course.description}</p>
      <button
        onClick={() => navigateTo('course', course)}
        className="w-full py-2 bg-indigo-500 text-white rounded-lg font-semibold hover:bg-indigo-600 transition-colors duration-300"
      >
        Start Course
      </button>
    </div>
  );
}

// Course/Chat Page Component
function CoursePage({ navigateTo, course }) {
  const [messages, setMessages] = useState([]);
  const [input, setInput] = useState('');
  const [isTyping, setIsTyping] = useState(false);

  // Function to handle sending a new message to the AI teacher
  const handleSendMessage = async (e) => {
    e.preventDefault();
    if (!input.trim()) return;

    // Add user's message to the chat history
    const newUserMessage = { sender: 'user', text: input };
    const newMessages = [...messages, newUserMessage];
    setMessages(newMessages);
    setInput('');
    setIsTyping(true);

    // Simulate an AI response by making an API call to the Gemini API
    const chatHistory = newMessages.map(msg => ({
      role: msg.sender === 'user' ? 'user' : 'model',
      parts: [{ text: msg.text }]
    }));

    // The prompt for the AI to act as the specific teacher
    const prompt = `You are a helpful and knowledgeable AI teacher named ${course.teacher} specializing in ${course.subject}. Respond to the student's question in a clear, educational, and friendly manner. The user asks: "${input}"`;

    chatHistory.push({ role: "user", parts: [{ text: prompt }] });
    const payload = { contents: chatHistory };
    const apiKey = "";
    const apiUrl = `https://generativelanguage.googleapis.com/v1beta/models/gemini-2.5-flash-preview-05-20:generateContent?key=${apiKey}`;

    try {
      const response = await fetch(apiUrl, {
        method: 'POST',
        headers: { 'Content-Type': 'application/json' },
        body: JSON.stringify(payload)
      });
      const result = await response.json();
      const aiResponseText = result.candidates?.[0]?.content?.parts?.[0]?.text;
      const newAiMessage = { sender: 'ai', text: aiResponseText || "Sorry, I couldn't generate a response." };
      setMessages(prevMessages => [...prevMessages, newAiMessage]);
    } catch (error) {
      console.error('API call failed:', error);
      const errorMessage = { sender: 'ai', text: 'Oops! Something went wrong. Please try again.' };
      setMessages(prevMessages => [...prevMessages, errorMessage]);
    } finally {
      setIsTyping(false);
    }
  };

  return (
    <div className="w-full flex flex-col h-[70vh]">
      <div className="flex justify-between items-center mb-4 pb-4 border-b border-gray-200">
        <div className="flex items-center">
          <img src={course.icon} alt="Course icon" className="w-10 h-10 rounded-full mr-3" />
          <div>
            <h2 className="text-2xl font-bold text-gray-800">{course.title}</h2>
            <p className="text-sm text-gray-500">Taught by {course.teacher}</p>
          </div>
        </div>
        <button
          onClick={() => navigateTo('dashboard')}
          className="px-4 py-2 text-sm bg-gray-200 text-gray-800 rounded-lg shadow-sm hover:bg-gray-300 transition-colors duration-300"
        >
          Back to Dashboard
        </button>
      </div>

      <div className="flex-1 overflow-y-auto p-4 bg-gray-100 rounded-lg shadow-inner mb-4">
        {messages.length === 0 ? (
          <div className="text-center text-gray-500 italic mt-10">
            Say hello to {course.teacher} to start your lesson!
          </div>
        ) : (
          messages.map((message, index) => (
            <div
              key={index}
              className={`flex mb-4 ${message.sender === 'user' ? 'justify-end' : 'justify-start'}`}
            >
              <div
                className={`max-w-xs md:max-w-md p-3 rounded-xl shadow-md ${
                  message.sender === 'user'
                    ? 'bg-indigo-500 text-white rounded-br-none'
                    : 'bg-white text-gray-800 rounded-bl-none'
                }`}
              >
                {message.text}
              </div>
            </div>
          ))
        )}
        {isTyping && (
          <div className="flex justify-start">
            <div className="max-w-md p-3 rounded-xl shadow-md bg-white text-gray-800 rounded-bl-none">
              <div className="flex space-x-1">
                <span className="animate-pulse w-2 h-2 bg-gray-400 rounded-full"></span>
                <span className="animate-pulse w-2 h-2 bg-gray-400 rounded-full delay-100"></span>
                <span className="animate-pulse w-2 h-2 bg-gray-400 rounded-full delay-200"></span>
              </div>
            </div>
          </div>
        )}
      </div>

      <form onSubmit={handleSendMessage} className="flex space-x-2">
        <input
          type="text"
          value={input}
          onChange={(e) => setInput(e.target.value)}
          placeholder="Ask a question..."
          className="flex-1 p-3 border border-gray-300 rounded-lg focus:outline-none focus:ring-2 focus:ring-indigo-500"
        />
        <button
          type="submit"
          className="px-6 py-3 bg-indigo-600 text-white font-semibold rounded-lg shadow-md hover:bg-indigo-700 transition-colors duration-300 disabled:bg-gray-400"
          disabled={isTyping || !input.trim()}
        >
          Send
        </button>
      </form>
    </div>
  );
}

