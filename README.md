import { motion } from 'motion/react';
import { Instagram, Music } from 'lucide-react';

const socials = [
  {
    name: 'Instagram',
    icon: Instagram,
    username: '@amaadeusdaniel',
    color: 'from-pink-500 to-purple-600',
    link: 'https://www.instagram.com/amaadeusdaniel'
  },
  {
    name: 'TikTok',
    icon: Music,
    username: '@traarizz',
    color: 'from-cyan-500 to-blue-600',
    link: 'https://www.tiktok.com/@traarizz'
  }
];

export function Contact() {
  return (
    <section className="py-24 px-6">
      <div className="max-w-6xl mx-auto">
        {/* Section Title */}
        <motion.div
          initial={{ opacity: 0, y: 20 }}
          whileInView={{ opacity: 1, y: 0 }}
          viewport={{ once: true }}
          transition={{ duration: 0.6 }}
          className="text-center mb-16"
        >
          <h2 className="text-4xl md:text-5xl font-bold mb-4 bg-gradient-to-r from-cyan-400 to-purple-600 text-transparent bg-clip-text">
            Let's Connect
          </h2>
          <p className="text-gray-400 text-lg">Mari terhubung dan berbagi pengalaman!</p>
        </motion.div>

        {/* Social Links */}
        <div className="grid md:grid-cols-2 gap-8 max-w-4xl mx-auto mb-16">
          {socials.map((social, index) => {
            const Icon = social.icon;
            
            return (
              <motion.a
                key={index}
                href={social.link}
                target="_blank"
                rel="noopener noreferrer"
                initial={{ opacity: 0, y: 20 }}
                whileInView={{ opacity: 1, y: 0 }}
                viewport={{ once: true }}
                transition={{ duration: 0.6, delay: index * 0.2 }}
                whileHover={{ scale: 1.05 }}
                className="block"
              >
                <div className="bg-gradient-to-br from-cyan-500/10 to-purple-500/10 backdrop-blur-sm border border-cyan-500/20 rounded-3xl p-8 hover:border-cyan-500/40 transition-all">
                  <div className="flex items-center gap-6">
                    <div className={`w-20 h-20 bg-gradient-to-br ${social.color} rounded-2xl flex items-center justify-center shadow-lg flex-shrink-0`}>
                      <Icon className="w-10 h-10 text-white" />
                    </div>
                    <div>
                      <h3 className="text-2xl font-bold text-white mb-2">{social.name}</h3>
                      <p className="text-cyan-400 text-lg">{social.username}</p>
                    </div>
                  </div>
                </div>
              </motion.a>
            );
          })}
        </div>

        {/* Footer */}
        <motion.div
          initial={{ opacity: 0 }}
          whileInView={{ opacity: 1 }}
          viewport={{ once: true }}
          transition={{ duration: 0.6 }}
          className="text-center"
        >
          <div className="inline-block bg-gradient-to-r from-cyan-500/10 to-purple-500/10 backdrop-blur-sm border border-cyan-500/20 rounded-full px-8 py-4">
            <p className="text-gray-400">
              Made with ❤️ by <span className="text-cyan-400 font-semibold">Amadeus Daniel Adisaputra</span>
            </p>
          </div>
          
          <div className="mt-8 text-gray-500 text-sm">
            © 2026 • Junior Data Analyst Journey
          </div>
        </motion.div>
      </div>
    </section>
  );
}
