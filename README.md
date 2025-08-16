import { motion } from "framer-motion";
import { Card, CardContent } from "@/components/ui/card";
import { Button } from "@/components/ui/button";
import { Github, Linkedin, Mail } from "lucide-react";

export default function Portfolio() {
  const projects = [
    { title: "IMG_1067", img: "/projects/IMG_1067.jpeg", link: "#" },
    { title: "IMG_1068", img: "/projects/IMG_1068.jpeg", link: "#" },
    { title: "IMG_1069", img: "/projects/IMG_1069.jpeg", link: "#" },
    { title: "IMG_1070", img: "/projects/IMG_1070.jpeg", link: "#" },
    { title: "IMG_1077", img: "/projects/IMG_1077.jpeg", link: "#" },
    { title: "IMG_1078", img: "/projects/IMG_1078.jpeg", link: "#" },
    { title: "IMG_1080", img: "/projects/IMG_1080.jpeg", link: "#" },
    { title: "IMG_1081", img: "/projects/IMG_1081.jpeg", link: "#" },
    { title: "IMG_1082", img: "/projects/IMG_1082.jpeg", link: "#" },
    { title: "IMG_1083", img: "/projects/IMG_1083.jpeg", link: "#" },
    { title: "IMG_1084", img: "/projects/IMG_1084.jpeg", link: "#" },
    { title: "IMG_1085", img: "/projects/IMG_1085.jpeg", link: "#" },
    { title: "IMG_1086", img: "/projects/IMG_1086.jpeg", link: "#" },
    { title: "IMG_1087", img: "/projects/IMG_1087.jpeg", link: "#" },
    { title: "IMG_1088", img: "/projects/IMG_1088.jpeg", link: "#" },
  ];

  return (
    <div className="min-h-screen bg-gray-950 text-white px-6 py-10">
      <motion.div
        initial={{ opacity: 0, y: -30 }}
        animate={{ opacity: 1, y: 0 }}
        transition={{ duration: 0.8 }}
        className="text-center mb-16"
      >
        <h1 className="text-5xl font-bold mb-4 bg-gradient-to-r from-blue-400 to-purple-500 bg-clip-text text-transparent">
          Your Name
        </h1>
        <p className="text-lg text-gray-400 max-w-2xl mx-auto">
          Professional Game Developer & Full-Stack Engineer. Passionate about
          creating immersive experiences with clean, scalable code.
        </p>
        <div className="flex justify-center gap-6 mt-6">
          <a href="https://github.com/your-username"><Github /></a>
          <a href="https://linkedin.com/in/your-username"><Linkedin /></a>
          <a href="mailto:your.email@example.com"><Mail /></a>
        </div>
      </motion.div>

      <h2 className="text-3xl font-semibold mb-8 text-center">Portfolio Gallery</h2>
      <div className="grid md:grid-cols-3 gap-8">
        {projects.map((proj, i) => (
          <motion.div key={i} whileHover={{ scale: 1.05 }}>
            <Card className="bg-gray-900 border border-gray-800 shadow-xl rounded-2xl overflow-hidden">
              <img src={proj.img} alt={proj.title} className="w-full h-64 object-cover" />
              <CardContent className="p-6">
                <h3 className="text-xl font-bold mb-2">{proj.title}</h3>
                <a href={proj.link} target="_blank">
                  <Button variant="outline" className="rounded-xl">View</Button>
                </a>
              </CardContent>
            </Card>
          </motion.div>
        ))}
      </div>

      <motion.footer
        initial={{ opacity: 0 }}
        animate={{ opacity: 1 }}
        transition={{ delay: 0.5 }}
        className="text-center mt-20 text-gray-500"
      >
        © {new Date().getFullYear()} Your Name. Built with ❤️ using React & Tailwind.
      </motion.footer>
    </div>
  );
}
