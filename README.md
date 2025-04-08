import React from "react";
import { Button } from "@/components/ui/button";
import { Card, CardContent } from "@/components/ui/card";
import { ShoppingCart } from "lucide-react";
import { motion } from "framer-motion";

export default function Home() {
  return (
    <div className="min-h-screen bg-gradient-to-br from-green-100 via-lime-50 to-emerald-100 text-green-900 font-sans">
      <header className="text-center py-10">
        <motion.h1
          initial={{ opacity: 0, y: -20 }}
          animate={{ opacity: 1, y: 0 }}
          transition={{ duration: 0.8 }}
          className="text-5xl font-bold"
        >
          GROVANA
        </motion.h1>
        <p className="mt-2 text-xl italic">
          Authentic Taste, Unmatched Quality
        </p>
        <img
          src="/logo.png"
          alt="Grovana Logo"
          className="mx-auto mt-4 w-24 h-24 rounded-full shadow-lg border-4 border-green-200"
        />
      </header>

      <main className="grid grid-cols-1 md:grid-cols-3 gap-6 px-6 pb-10">
        {["Herbal Green Tea", "Tulsi Detox Tea", "Mint Ginger Tea"].map((tea, i) => (
          <motion.div
            key={i}
            initial={{ opacity: 0, y: 20 }}
            animate={{ opacity: 1, y: 0 }}
            transition={{ delay: 0.2 * i }}
          >
            <Card className="rounded-2xl shadow-md bg-white">
              <CardContent className="p-6">
                <h3 className="text-2xl font-semibold mb-2">{tea}</h3>
                <p className="text-green-700 mb-4">
                  Pure organic ingredients handpicked from Indian farms.
                </p>
                <Button className="bg-green-600 hover:bg-green-700 text-white">
                  <ShoppingCart className="mr-2" size={18} /> Add to Cart
                </Button>
              </CardContent>
            </Card>
          </motion.div>
        ))}
      </main>

      <footer className="text-center py-6 text-sm text-green-800">
        &copy; 2025 R&G Organics | Address: Siliguri, West Bengal
      </footer>
    </div>
  );
}
