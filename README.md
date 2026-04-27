import { Link } from "react-router-dom";
import { Button } from "@/components/ui/button";
import { Card, CardContent } from "@/components/ui/card";
import { Badge } from "@/components/ui/badge";
import {
  ShieldCheck,
  Award,
  Truck,
  Users,
  Star,
  CheckCircle2,
  ArrowRight,
  Fish,
  Clock,
  HeartHandshake,
} from "lucide-react";
import Navbar from "@/components/Navbar";
import Footer from "@/components/Footer";
import { products, formatPrice, generateWhatsAppLink } from "@/data/products";

const Index = () => {
  const featured = products.filter((p) => p.bestSeller).slice(0, 4);

  const testimonials = [
    {
      name: "Budi Santoso",
      location: "Surabaya",
      rating: 5,
      text: "Pesan Motoro sampai dengan kondisi prima. Packing sangat rapi dan profesional. Admin juga sangat responsif menjawab pertanyaan. Recommended!",
    },
    {
      name: "Rahman Hakim",
      location: "Bandung",
      rating: 5,
      text: "Sudah langganan beli pari disini sejak 3 tahun lalu. Kualitas selalu konsisten dan harga fair. Leopoldi yang saya beli sekarang sudah besar dan sehat.",
    },
    {
      name: "Dewi Lestari",
      location: "Medan",
      rating: 5,
      text: "Pengiriman ke Medan aman sampai tujuan, ikan sehat dan sesuai foto. After sales service juga bagus, selalu bantu konsultasi perawatan.",
    },
  ];

  return (
    <div className="min-h-screen bg-white">
      <Navbar />

      {/* Hero Section */}
      <section className="relative overflow-hidden">
        <div
          className="relative h-[600px] md:h-[650px] bg-cover bg-center"
          style={{
            backgroundImage:
              "url('https://mgx-backend-cdn.metadl.com/generate/images/1158769/2026-04-27/nnqjpqaaafla/hero-stingray-aquarium.png')",
          }}
        >
          <div className="absolute inset-0 bg-gradient-to-r from-[#0A4D8C]/90 via-[#0A4D8C]/70 to-transparent" />
          <div className="relative max-w-7xl mx-auto px-4 h-full flex items-center">
            <div className="max-w-2xl text-white">
              <Badge className="mb-4 bg-[#F59E0B] hover:bg-[#F59E0B] text-white border-0 px-3 py-1">
                🏆 #1 Trusted Stingray Breeder di Indonesia
              </Badge>
              <h1 className="text-4xl md:text-6xl font-bold mb-6 leading-tight">
                Ikan Pari Hias <span className="text-[#F59E0B]">Premium</span> Langsung dari Breeder Terpercaya
              </h1>
              <p className="text-lg md:text-xl mb-8 text-blue-50">
                Koleksi ikan pari hias kualitas export: Motoro, Leopoldi, Black Diamond, dan Galaxy. Garansi hidup 100% sampai tujuan dengan pengalaman 10+ tahun.
              </p>
              <div className="flex flex-wrap gap-4">
                <Link to="/katalog">
                  <Button size="lg" className="bg-[#F59E0B] hover:bg-[#D97706] text-white shadow-lg">
                    Lihat Katalog <ArrowRight className="ml-2 w-5 h-5" />
                  </Button>
                </Link>
                <a href={generateWhatsAppLink()} target="_blank" rel="noopener noreferrer">
                  <Button
                    size="lg"
                    variant="outline"
                    className="!bg-transparent !hover:bg-white/10 border-white text-white hover:text-white"
                  >
                    💬 Konsultasi Gratis
                  </Button>
                </a>
              </div>
              <div className="mt-8 flex flex-wrap gap-6 text-sm">
                <div className="flex items-center gap-2">
                  <CheckCircle2 className="w-5 h-5 text-[#10B981]" />
                  <span>Garansi Hidup</span>
                </div>
                <div className="flex items-center gap-2">
                  <CheckCircle2 className="w-5 h-5 text-[#10B981]" />
                  <span>Sertifikat Kesehatan</span>
                </div>
                <div className="flex items-center gap-2">
                  <CheckCircle2 className="w-5 h-5 text-[#10B981]" />
                  <span>Kirim Seluruh Indonesia</span>
                </div>
              </div>
            </div>
          </div>
        </div>
      </section>

      {/* Stats Section */}
      <section className="bg-[#E0F2FE] py-10">
        <div className="max-w-7xl mx-auto px-4 grid grid-cols-2 md:grid-cols-4 gap-6">
          {[
            { icon: Users, value: "5,000+", label: "Pelanggan Puas" },
            { icon: Clock, value: "10+", label: "Tahun Pengalaman" },
            { icon: Truck, value: "15,000+", label: "Pengiriman Sukses" },
            { icon: Award, value: "100%", label: "Garansi Hidup" },
          ].map((stat, idx) => (
            <div key={idx} className="text-center">
              <div className="w-14 h-14 bg-[#0A4D8C] rounded-full flex items-center justify-center mx-auto mb-3">
                <stat.icon className="w-7 h-7 text-white" />
              </div>
              <div className="text-3xl font-bold text-[#0C1E3E]">{stat.value}</div>
              <div className="text-sm text-gray-600">{stat.label}</div>
            </div>
          ))}
        </div>
      </section>

      {/* Why Choose Us */}
      <section className="py-16 px-4">
        <div className="max-w-7xl mx-auto">
          <div className="text-center mb-12">
            <Badge className="mb-3 bg-blue-50 text-[#0A4D8C] hover:bg-blue-50 border-0">
              Mengapa Memilih Kami
            </Badge>
            <h2 className="text-3xl md:text-4xl font-bold text-[#0C1E3E] mb-4">
              Kepercayaan Anda Adalah Prioritas Kami
            </h2>
            <p className="text-gray-600 max-w-2xl mx-auto">
              Dengan pengalaman lebih dari 10 tahun sebagai breeder ikan pari hias,
              kami berkomitmen memberikan produk berkualitas terbaik dan pelayanan profesional.
            </p>
          </div>

          <div className="grid grid-cols-1 md:grid-cols-3 gap-6">
            {[
              {
                icon: ShieldCheck,
                title: "Garansi Hidup 100%",
                desc: "Setiap ikan pari kami jamin sehat dan hidup sampai ke alamat Anda. Jika ada masalah, kami ganti dengan yang baru.",
              },
              {
                icon: Award,
                title: "Breeder Profesional",
                desc: "Tim breeder kami adalah ahli berpengalaman yang merawat induk-induk berkualitas dengan standar tinggi sejak 2015.",
              },
              {
                icon: HeartHandshake,
                title: "After Sales Service",
                desc: "Konsultasi perawatan gratis seumur hidup. Tim kami siap membantu Anda merawat ikan pari Anda dengan baik.",
              },
            ].map((item, idx) => (
              <Card key={idx} className="border-blue-100 hover:shadow-xl transition-shadow duration-300">
                <CardContent className="p-6">
                  <div className="w-14 h-14 bg-gradient-to-br from-[#0A4D8C] to-[#38BDF8] rounded-xl flex items-center justify-center mb-4 shadow-md">
                    <item.icon className="w-7 h-7 text-white" />
                  </div>
                  <h3 className="text-xl font-bold text-[#0C1E3E] mb-2">{item.title}</h3>
                  <p className="text-gray-600 text-sm leading-relaxed">{item.desc}</p>
                </CardContent>
              </Card>
            ))}
          </div>
        </div>
      </section>

      {/* Featured Products */}
      <section className="bg-[#E0F2FE]/40 py-16 px-4">
        <div className="max-w-7xl mx-auto">
          <div className="flex flex-col md:flex-row md:items-end justify-between mb-10 gap-4">
            <div>
              <Badge className="mb-3 bg-[#F59E0B]/10 text-[#F59E0B] hover:bg-[#F59E0B]/10 border-0">
                ⭐ Best Seller
              </Badge>
              <h2 className="text-3xl md:text-4xl font-bold text-[#0C1E3E]">
                Koleksi Pari Unggulan
              </h2>
              <p className="text-gray-600 mt-2">Pilihan terbaik dengan kualitas premium</p>
            </div>
            <Link to="/katalog">
              <Button variant="outline" className="border-[#0A4D8C] text-[#0A4D8C] hover:bg-[#0A4D8C] hover:text-white">
                Lihat Semua <ArrowRight className="ml-2 w-4 h-4" />
              </Button>
            </Link>
          </div>

          <div className="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-4 gap-6">
            {featured.map((product) => (
              <Card
                key={product.id}
                className="overflow-hidden border-blue-100 hover:shadow-2xl transition-all duration-300 group"
              >
                <div className="relative overflow-hidden aspect-square bg-blue-50">
                  <img
                    src={product.image}
                    alt={product.name}
                    className="w-full h-full object-cover group-hover:scale-110 transition-transform duration-500"
                  />
                  <div className="absolute top-3 left-3 flex flex-col gap-1">
                    {product.bestSeller && (
                      <Badge className="bg-[#F59E0B] hover:bg-[#F59E0B] text-white border-0">
                        Best Seller
                      </Badge>
                    )}
                    {product.limited && (
                      <Badge className="bg-red-500 hover:bg-red-500 text-white border-0">
                        Limited Stock
                      </Badge>
                    )}
                  </div>
                </div>
                <CardContent className="p-4">
                  <div className="text-xs text-[#0A4D8C] font-medium mb-1">{product.category}</div>
                  <h3 className="font-bold text-[#0C1E3E] mb-1 line-clamp-1">{product.name}</h3>
                  <div className="text-xs text-gray-500 mb-2">{product.size} • {product.gender}</div>
                  <div className="text-lg font-bold text-[#0A4D8C] mb-3">
                    {formatPrice(product.price)}
                  </div>
                  <Link to={`/produk/${product.id}`}>
                    <Button className="w-full bg-[#0A4D8C] hover:bg-[#083a6b] text-white">
                      Lihat Detail
                    </Button>
                  </Link>
                </CardContent>
              </Card>
            ))}
          </div>
        </div>
      </section>

      {/* Testimonials */}
      <section className="py-16 px-4">
        <div className="max-w-7xl mx-auto">
          <div className="text-center mb-12">
            <Badge className="mb-3 bg-blue-50 text-[#0A4D8C] hover:bg-blue-50 border-0">
              Testimoni Pelanggan
            </Badge>
            <h2 className="text-3xl md:text-4xl font-bold text-[#0C1E3E] mb-4">
              Apa Kata Pelanggan Kami
            </h2>
            <p className="text-gray-600 max-w-2xl mx-auto">
              Kepuasan pelanggan adalah bukti kualitas kami
            </p>
          </div>

          <div className="grid grid-cols-1 md:grid-cols-3 gap-6">
            {testimonials.map((t, idx) => (
              <Card key={idx} className="border-blue-100 hover:shadow-lg transition-shadow">
                <CardContent className="p-6">
                  <div className="flex gap-1 mb-3">
                    {[...Array(t.rating)].map((_, i) => (
                      <Star key={i} className="w-4 h-4 fill-[#F59E0B] text-[#F59E0B]" />
                    ))}
                  </div>
                  <p className="text-gray-700 mb-4 italic leading-relaxed">"{t.text}"</p>
                  <div className="flex items-center gap-3 pt-4 border-t border-blue-100">
                    <div className="w-10 h-10 bg-gradient-to-br from-[#0A4D8C] to-[#38BDF8] rounded-full flex items-center justify-center text-white font-bold">
                      {t.name.charAt(0)}
                    </div>
                    <div>
                      <div className="font-semibold text-[#0C1E3E]">{t.name}</div>
                      <div className="text-xs text-gray-500">{t.location}</div>
                    </div>
                  </div>
                </CardContent>
              </Card>
            ))}
          </div>
        </div>
      </section>

      {/* Guarantee Section */}
      <section className="bg-gradient-to-br from-[#0A4D8C] to-[#0C1E3E] py-16 px-4 text-white">
        <div className="max-w-7xl mx-auto grid grid-cols-1 md:grid-cols-2 gap-10 items-center">
          <div>
            <Badge className="mb-3 bg-[#F59E0B] hover:bg-[#F59E0B] text-white border-0">
              Jaminan Kami
            </Badge>
            <h2 className="text-3xl md:text-4xl font-bold mb-6">
              Pengiriman Aman dengan Packing Profesional
            </h2>
            <p className="text-blue-100 mb-6 leading-relaxed">
              Kami menggunakan metode packing standar internasional dengan oksigen murni dan
              double bagging. Setiap pengiriman dilengkapi dengan asuransi dan tracking real-time.
            </p>
            <div className="space-y-3">
              {[
                "Packing dengan oksigen murni & double bag",
                "Asuransi pengiriman sampai tujuan",
                "Estimasi pengiriman 1-3 hari via ekspedisi terpercaya",
                "Garansi replace jika ada kendala dalam 24 jam",
              ].map((item, idx) => (
                <div key={idx} className="flex items-center gap-3">
                  <CheckCircle2 className="w-5 h-5 text-[#10B981] flex-shrink-0" />
                  <span>{item}</span>
                </div>
              ))}
            </div>
          </div>
          <div className="rounded-xl overflow-hidden shadow-2xl">
            <img
              src="https://mgx-backend-cdn.metadl.com/generate/images/1158769/2026-04-27/nnqkcsiaaflq/packing-process.png"
              alt="Proses packing profesional"
              className="w-full h-full object-cover"
            />
          </div>
        </div>
      </section>

      {/* CTA Section */}
      <section className="py-16 px-4 bg-white">
        <div className="max-w-4xl mx-auto text-center">
          <Fish className="w-16 h-16 text-[#0A4D8C] mx-auto mb-4" />
          <h2 className="text-3xl md:text-4xl font-bold text-[#0C1E3E] mb-4">
            Siap Menambah Koleksi Ikan Pari Anda?
          </h2>
          <p className="text-gray-600 mb-8 max-w-2xl mx-auto">
            Konsultasikan kebutuhan ikan pari Anda dengan tim ahli kami. Kami siap membantu
            memilih pari yang tepat untuk akuarium Anda.
          </p>
          <div className="flex flex-wrap justify-center gap-4">
            <Link to="/katalog">
              <Button size="lg" className="bg-[#0A4D8C] hover:bg-[#083a6b] text-white">
                Lihat Katalog Lengkap
              </Button>
            </Link>
            <a href={generateWhatsAppLink()} target="_blank" rel="noopener noreferrer">
              <Button size="lg" className="bg-green-600 hover:bg-green-700 text-white">
                💬 Chat via WhatsApp
              </Button>
            </a>
          </div>
        </div>
      </section>

      <Footer />

      {/* Floating WhatsApp Button */}
      <a
        href={generateWhatsAppLink()}
        target="_blank"
        rel="noopener noreferrer"
        className="fixed bottom-6 right-6 w-14 h-14 bg-green-500 hover:bg-green-600 rounded-full shadow-2xl flex items-center justify-center z-50 transition-transform hover:scale-110"
        aria-label="Chat WhatsApp"
      >
        <svg className="w-7 h-7 text-white" fill="currentColor" viewBox="0 0 24 24">
          <path d="M17.472 14.382c-.297-.149-1.758-.867-2.03-.967-.273-.099-.471-.148-.67.15-.197.297-.767.966-.94 1.164-.173.199-.347.223-.644.075-.297-.15-1.255-.463-2.39-1.475-.883-.788-1.48-1.761-1.653-2.059-.173-.297-.018-.458.13-.606.134-.133.298-.347.446-.52.149-.174.198-.298.298-.497.099-.198.05-.371-.025-.52-.075-.149-.669-1.612-.916-2.207-.242-.579-.487-.5-.669-.51-.173-.008-.371-.01-.57-.01-.198 0-.52.074-.792.372-.272.297-1.04 1.016-1.04 2.479 0 1.462 1.065 2.875 1.213 3.074.149.198 2.096 3.2 5.077 4.487.709.306 1.262.489 1.694.625.712.227 1.36.195 1.871.118.571-.085 1.758-.719 2.006-1.413.248-.694.248-1.289.173-1.413-.074-.124-.272-.198-.57-.347m-5.421 7.403h-.004a9.87 9.87 0 01-5.031-1.378l-.361-.214-3.741.982.998-3.648-.235-.374a9.86 9.86 0 01-1.51-5.26c.001-5.45 4.436-9.884 9.888-9.884 2.64 0 5.122 1.03 6.988 2.898a9.825 9.825 0 012.893 6.994c-.003 5.45-4.437 9.884-9.885 9.884m8.413-18.297A11.815 11.815 0 0012.05 0C5.495 0 .16 5.335.157 11.892c0 2.096.547 4.142 1.588 5.945L.057 24l6.305-1.654a11.882 11.882 0 005.683 1.448h.005c6.554 0 11.89-5.335 11.893-11.893a11.821 11.821 0 00-3.48-8.413z"/>
        </svg>
      </a>
    </div>
  );
};

export default Index;
