import { useState, useEffect } from 'react'
import Image from 'next/image'
import Link from "next/link"
import { Button } from "@/components/ui/button"
import { Card, CardContent } from "@/components/ui/card"
import { Facebook, Instagram, Twitter, Menu, X, Coffee, Code, Calculator, Users } from "lucide-react"

const socialMediaPosts = [
  { id: 1, platform: "twitter", content: "🎉 Pizza & Programming night this Friday! #UPEICode" },
  { id: 2, platform: "instagram", content: "📸 Swipe to see the winners of our Math Meme Contest! 😂" },
  { id: 3, platform: "facebook", content: "🧠 New AI workshop series starting next week. Sign up now!" },
]

const events = [
  { id: 1, name: "Hackathon 2023", date: "Oct 15-17", icon: Code },
  { id: 2, name: "Math Quiz Night", date: "Oct 22", icon: Calculator },
  { id: 3, name: "Coffee & Coding", date: "Every Tuesday", icon: Coffee },
]

export default function MainPage() {
  const [isMenuOpen, setIsMenuOpen] = useState(false)
  const [bgPosition, setBgPosition] = useState({ x: 0, y: 0 })

  useEffect(() => {
    const handleMouseMove = (e: MouseEvent) => {
      setBgPosition({ x: e.clientX, y: e.clientY })
    }
    window.addEventListener('mousemove', handleMouseMove)
    return () => window.removeEventListener('mousemove', handleMouseMove)
  }, [])

  return (
    <div className="flex flex-col min-h-screen bg-black text-white overflow-hidden">
      <div 
        className="fixed inset-0 opacity-20"
        style={{
          backgroundImage: `radial-gradient(circle at ${bgPosition.x}px ${bgPosition.y}px, rgba(255,165,0,0.3) 0%, rgba(0,255,255,0.3) 50%, transparent 70%)`,
          transition: 'background 0.3s ease',
        }}
      />
      <div className="fixed inset-0 opacity-10">
        {[...Array(100)].map((_, i) => (
          <div
            key={i}
            className="absolute text-xs text-gray-500"
            style={{
              left: `${Math.random() * 100}%`,
              top: `${Math.random() * 100}%`,
              transform: `rotate(${Math.random() * 360}deg)`,
            }}
          >
            {Math.random() > 0.5 ? 'π' : '∑'}
          </div>
        ))}
      </div>
      <header className="bg-black bg-opacity-80 text-white shadow-md sticky top-0 z-10">
        <nav className="container mx-auto px-4 py-4 flex justify-between items-center">
          <Link href="/" className="text-2xl font-bold flex items-center">
            <Image src="https://hebbkx1anhila5yf.public.blob.vercel-storage.com/Logo%20(Black%20Background)-RtIFkP9qCwJDpd7ga6aGdzmqkSFsmp.png" alt="SMCSS Logo" width={50} height={50} className="mr-2" />
            <span className="sr-only">UPEI SMSCSS</span>
          </Link>
          <div className="hidden md:flex space-x-4">
            <Link href="/about" className="hover:text-orange-400">About Us</Link>
            <Link href="/resources" className="hover:text-orange-400">Resources</Link>
            <Link href="/events" className="hover:text-orange-400">Events</Link>
            <Link href="/contact" className="hover:text-orange-400">Contact</Link>
          </div>
          <Button variant="outline" className="md:hidden text-white border-white hover:bg-white hover:text-black" onClick={() => setIsMenuOpen(!isMenuOpen)}>
            {isMenuOpen ? <X /> : <Menu />}
          </Button>
        </nav>
        {isMenuOpen && (
          <div className="md:hidden bg-black bg-opacity-80 py-2">
            <Link href="/about" className="block px-4 py-2 hover:bg-white hover:text-black">About Us</Link>
            <Link href="/resources" className="block px-4 py-2 hover:bg-white hover:text-black">Resources</Link>
            <Link href="/events" className="block px-4 py-2 hover:bg-white hover:text-black">Events</Link>
            <Link href="/contact" className="block px-4 py-2 hover:bg-white hover:text-black">Contact</Link>
          </div>
        )}
      </header>

      <main className="flex-grow container mx-auto px-4 py-8 relative z-10">
        <section className="text-center mb-12 animate-fade-in-down">
          <h1 className="text-5xl font-bold mb-4 text-white">Welcome to UPEI SMSCSS</h1>
          <p className="text-xl mb-8 text-gray-300">Where Math Meets Code and Friendships Compute!</p>
          <div className="max-w-4xl mx-auto bg-white bg-opacity-10 p-4 rounded-lg">
            <h2 className="text-2xl font-bold mb-4 text-white">Join Us!</h2>
            <div className="relative overflow-hidden pb-[177%] h-0">
              <iframe 
                src="https://docs.google.com/forms/d/e/1FAIpQLSffXJVTLdvbtSC3zNE1o-bIVSWoUDO3EfjlHTFk5L-rFVZlOA/viewform?embedded=true" 
                className="absolute top-0 left-0 w-full h-full"
                style={{border: 0}}
                title="UPEI SMSCSS Signup Form"
              >
                Loading…
              </iframe>
            </div>
          </div>
        </section>

        <section className="mb-12 animate-fade-in-up">
          <h2 className="text-3xl font-bold mb-4 text-center text-white">Upcoming Events</h2>
          <div className="grid grid-cols-1 md:grid-cols-3 gap-4">
            {events.map((event) => (
              <Card key={event.id} className="bg-white bg-opacity-10 hover:bg-opacity-20 transition-all duration-300">
                <CardContent className="p-6 flex items-center">
                  <event.icon className="w-12 h-12 text-orange-400 mr-4" />
                  <div>
                    <h3 className="text-xl font-semibold text-white">{event.name}</h3>
                    <p className="text-gray-300">{event.date}</p>
                  </div>
                </CardContent>
              </Card>
            ))}
          </div>
        </section>

        <section className="mb-12 animate-fade-in-up">
          <h2 className="text-3xl font-bold mb-4 text-center text-white">Latest Updates</h2>
          <div className="grid grid-cols-1 md:grid-cols-3 gap-4">
            {socialMediaPosts.map((post) => (
              <Card key={post.id} className="bg-white bg-opacity-10 hover:bg-opacity-20 transition-all duration-300">
                <CardContent className="p-6">
                  <div className="flex items-center mb-2">
                    {post.platform === "twitter" && <Twitter className="mr-2 text-cyan-300" />}
                    {post.platform === "instagram" && <Instagram className="mr-2 text-orange-400" />}
                    {post.platform === "facebook" && <Facebook className="mr-2 text-cyan-300" />}
                    <span className="capitalize font-semibold text-white">{post.platform}</span>
                  </div>
                  <p className="text-gray-300">{post.content}</p>
                </CardContent>
              </Card>
            ))}
          </div>
        </section>

        <section className="text-center mb-12 animate-fade-in-up">
          <h2 className="text-3xl font-bold mb-4 text-white">Why Join SMSCSS?</h2>
          <div className="grid grid-cols-1 md:grid-cols-3 gap-8">
            <div>
              <Users className="w-16 h-16 mx-auto text-orange-400 mb-4" />
              <h3 className="text-xl font-semibold mb-2 text-white">Community</h3>
              <p className="text-gray-300">Connect with fellow math and CS enthusiasts</p>
            </div>
            <div>
              <Code className="w-16 h-16 mx-auto text-cyan-300 mb-4" />
              <h3 className="text-xl font-semibold mb-2 text-white">Learning</h3>
              <p className="text-gray-300">Enhance your skills through workshops and projects</p>
            </div>
            <div>
              <Coffee className="w-16 h-16 mx-auto text-orange-400 mb-4" />
              <h3 className="text-xl font-semibold mb-2 text-white">Fun</h3>
              <p className="text-gray-300">Enjoy social events and make lasting friendships</p>
            </div>
          </div>
        </section>
      </main>

      <footer className="bg-black bg-opacity-80 mt-12 relative z-10">
        <div className="container mx-auto px-4 py-6 flex flex-col md:flex-row justify-between items-center">
          <p className="text-gray-300">&copy; {new Date().getFullYear()} UPEI SMSCSS. All rights reserved.</p>
          <div className="flex space-x-4 mt-4 md:mt-0">
            <a href="#" className="text-cyan-300 hover:text-orange-400"><Twitter /></a>
            <a href="#" className="text-orange-400 hover:text-cyan-300"><Instagram /></a>
            <a href="#" className="text-cyan-300 hover:text-orange-400"><Facebook /></a>
          </div>
        </div>
      </footer>
    </div>
  )
}
