import React, { useState, useEffect } from 'react';
import { Github, Twitter, Link, MapPin, Users, Star, Code, Award, Zap, BookOpen } from 'lucide-react';

const App = () => {
  const [profile, setProfile] = useState(null);
  const [repos, setRepos] = useState([]);
  const [loading, setLoading] = useState(true);
  const [error, setError] = useState(null);
  const username = 'ssomsakth';

  useEffect(() => {
    const fetchGithubData = async () => {
      try {
        setLoading(true);
        // Fetch profile data
        const profileRes = await fetch(`https://api.github.com/users/${username}`);
        if (!profileRes.ok) throw new Error('Failed to fetch profile data');
        const profileData = await profileRes.json();
        setProfile(profileData);

        // Fetch repos, sort by stars, and limit to top 8 for display
        const reposRes = await fetch(`https://api.github.com/users/${username}/repos?sort=stars&per_page=8`);
        if (!reposRes.ok) throw new Error('Failed to fetch repositories');
        const reposData = await reposRes.json();
        setRepos(reposData.sort((a, b) => b.stargazers_count - a.stargazers_count));

      } catch (e) {
        setError(e.message);
      } finally {
        setLoading(false);
      }
    };

    fetchGithubData();
  }, [username]);
  
  // Hardcoded data for Achievements and Highlights
  const achievements = [
    { id: 1, title: 'นักพัฒนา GitHub ระดับยอดเยี่ยม', description: 'ได้รับรางวัลจากความมุ่งมั่นในการทำโปรเจกต์โอเพนซอร์ส' },
    { id: 2, title: 'Contributor 100 โปรเจกต์', description: 'มีส่วนร่วมในโปรเจกต์โอเพนซอร์สมากกว่า 100 โปรเจกต์' },
    { id: 3, title: 'ผู้นำชุมชนโอเพนซอร์ส', description: 'สร้างและดูแลชุมชนนักพัฒนาโอเพนซอร์ส' },
  ];

  const highlights = [
    { id: 1, icon: Users, text: 'ชุมชนนักพัฒนามืออาชีพ' },
    { id: 2, icon: Code, text: 'เชี่ยวชาญด้าน JavaScript และ Python' },
    { id: 3, icon: Star, text: 'โปรเจกต์ยอดนิยมกว่า 1,000 ดาว' },
  ];

  if (loading) {
    return (
      <div className="flex items-center justify-center min-h-screen bg-gray-900 text-gray-200 p-4">
        <div className="flex items-center space-x-2">
          <svg className="animate-spin h-5 w-5 text-purple-400" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24">
            <circle className="opacity-25" cx="12" cy="12" r="10" stroke="currentColor" strokeWidth="4"></circle>
            <path className="opacity-75" fill="currentColor" d="M4 12a8 8 0 018-8V0C5.373 0 0 5.373 0 12h4zm2 5.291A7.962 7.962 0 014 12H0c0 3.042 1.135 5.824 3 7.938l3-2.647z"></path>
          </svg>
          <span>กำลังโหลดข้อมูล...</span>
        </div>
      </div>
    );
  }

  if (error) {
    return (
      <div className="flex items-center justify-center min-h-screen bg-gray-900 text-red-400 p-4">
        <p>เกิดข้อผิดพลาด: {error}</p>
      </div>
    );
  }
  
  return (
    <>
      <style>
        {`
          @import url('https://fonts.googleapis.com/css2?family=Sarabun:wght@400;700&display=swap');
          .font-sarabun {
            font-family: 'Sarabun', sans-serif;
          }
        `}
      </style>
      <div className="min-h-screen bg-gray-900 text-gray-200 font-sarabun p-4 sm:p-8 flex items-center justify-center">
        <div className="w-full max-w-4xl bg-gray-800 rounded-2xl shadow-xl overflow-hidden p-6 sm:p-10">
          
          {/* Profile Header */}
          <div className="flex flex-col sm:flex-row items-center sm:items-start space-y-6 sm:space-y-0 sm:space-x-8 mb-10 pb-6 border-b border-gray-700">
            <img
              src={profile.avatar_url}
              alt="โปรไฟล์"
              className="w-32 h-32 rounded-full border-4 border-purple-500 shadow-lg"
            />
            <div className="text-center sm:text-left flex-1">
              <h1 className="text-4xl sm:text-5xl font-bold text-white mb-2">{profile.name || username}</h1>
              <p className="text-xl text-gray-400 font-light mb-4">@{profile.login}</p>
              {profile.bio && <p className="text-md text-gray-300 max-w-lg mx-auto sm:mx-0">{profile.bio}</p>}
            </div>
            <div className="flex-shrink-0 flex sm:flex-col items-center sm:items-start space-x-4 sm:space-x-0 sm:space-y-2">
              <div className="flex items-center space-x-2">
                <Users size={18} className="text-purple-400" />
                <span className="text-sm">ผู้ติดตาม {profile.followers}</span>
                <span className="text-sm">กำลังติดตาม {profile.following}</span>
              </div>
            </div>
          </div>
  
          {/* Profile Details */}
          <div className="grid grid-cols-1 sm:grid-cols-2 gap-6 mb-10 pb-6 border-b border-gray-700">
            {profile.location && (
              <div className="flex items-center space-x-3">
                <MapPin size={20} className="text-purple-400" />
                <span className="text-md text-gray-300">อาศัยที่ {profile.location}</span>
              </div>
            )}
            {profile.blog && (
              <div className="flex items-center space-x-3">
                <Link size={20} className="text-purple-400" />
                <a href={profile.blog} target="_blank" rel="noopener noreferrer" className="text-md text-purple-300 hover:underline">
                  เว็บไซต์/บล็อก
                </a>
              </div>
            )}
            {profile.twitter_username && (
              <div className="flex items-center space-x-3">
                <Twitter size={20} className="text-purple-400" />
                <a href={`https://twitter.com/${profile.twitter_username}`} target="_blank" rel="noopener noreferrer" className="text-md text-purple-300 hover:underline">
                  @{profile.twitter_username}
                </a>
              </div>
            )}
          </div>

          {/* Highlights Section */}
          <div className="mb-10 pb-6 border-b border-gray-700">
            <h2 className="text-3xl font-bold text-white mb-6">จุดเด่น</h2>
            <div className="grid grid-cols-1 md:grid-cols-3 gap-6">
              {highlights.map(item => {
                const IconComponent = item.icon;
                return (
                  <div key={item.id} className="flex items-center space-x-4 p-4 bg-gray-700 rounded-xl shadow-lg">
                    <IconComponent size={32} className="text-purple-400 flex-shrink-0" />
                    <p className="text-lg text-gray-200">{item.text}</p>
                  </div>
                );
              })}
            </div>
          </div>

          {/* Achievements Section */}
          <div className="mb-10 pb-6 border-b border-gray-700">
            <h2 className="text-3xl font-bold text-white mb-6">ความสำเร็จ</h2>
            <div className="grid grid-cols-1 gap-4">
              {achievements.map(item => (
                <div key={item.id} className="flex items-center space-x-4 p-4 bg-gray-700 rounded-xl shadow-lg">
                  <Award size={32} className="text-yellow-400 flex-shrink-0" />
                  <div>
                    <h3 className="text-xl font-semibold text-white">{item.title}</h3>
                    <p className="text-sm text-gray-400">{item.description}</p>
                  </div>
                </div>
              ))}
            </div>
          </div>
  
          {/* Repositories Section */}
          <h2 className="text-3xl font-bold text-white mb-6">โปรเจกต์เด่น ({profile.public_repos})</h2>
          <div className="grid grid-cols-1 md:grid-cols-2 gap-6">
            {repos.map(repo => (
              <a 
                href={repo.html_url} 
                target="_blank" 
                rel="noopener noreferrer" 
                key={repo.id} 
                className="group block p-6 bg-gray-700 rounded-xl shadow-lg hover:shadow-2xl hover:bg-gray-600 transition-all duration-300"
              >
                <h3 className="text-xl font-semibold text-white group-hover:text-purple-300 transition-colors duration-300 mb-2">{repo.name}</h3>
                <p className="text-sm text-gray-400 mb-4">{repo.description || 'ไม่มีคำอธิบาย'}</p>
                <div className="flex items-center justify-between text-gray-400 text-sm">
                  <div className="flex items-center space-x-1">
                    <Code size={16} />
                    <span>{repo.language || 'ไม่ระบุ'}</span>
                  </div>
                  <div className="flex items-center space-x-1">
                    <Star size={16} />
                    <span>{repo.stargazers_count}</span>
                  </div>
                </div>
              </a>
            ))}
          </div>
  
          {/* GitHub Stats Card */}
          <div className="mt-10 pt-6 border-t border-gray-700">
            <h2 className="text-3xl font-bold text-white mb-6">สถิติ GitHub</h2>
            <div className="flex justify-center">
              <img 
                src="https://github-readme-stats.vercel.app/api?username=ssomsakth&show_icons=true&theme=dark&hide_border=true&border_radius=10&hide_rank=true" 
                alt="GitHub Stats" 
                className="w-full h-auto rounded-lg"
              />
            </div>
          </div>
  
        </div>
      </div>
    </>
  );
};

export default App;
