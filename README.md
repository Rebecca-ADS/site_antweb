// Estrutura de uma landing page simples para a empresa AntWeb
// Tecnologias: React + Tailwind CSS

import { useState } from 'react';

export default function LandingPageAntweb() {
  const [formData, setFormData] = useState({
    nome: '',
    email: '',
    telefone: ''
  });

  const handleChange = (e) => {
    setFormData({ ...formData, [e.target.name]: e.target.value });
  };

  const handleSubmit = (e) => {
    e.preventDefault();
    console.log('Dados enviados:', formData);
    alert('Cadastro enviado com sucesso! Em breve um consultor entrará em contato.');
    setFormData({ nome: '', email: '', telefone: '' });
  };

  return (
    <div className="min-h-screen bg-gray-800 flex items-center justify-between p-4 text-white relative">
      {/* Mensagem no canto inferior esquerdo */}
      <div className="absolute bottom-4 left-4 text-white font-bold text-lg">
        Montamos seu site com propósito e com máxima eficiência
      </div>

      {/* Imagem do lado esquerdo */}
      <div className="w-1/2 p-4 hidden md:block">
        <img 
          src="https://images.unsplash.com/photo-1517336714731-489689fd1ca8?auto=format&fit=crop&w=800&q=80" 
          alt="Notebook tecnológico" 
          className="rounded-2xl shadow-lg object-cover w-full h-full"
        />
      </div>

      {/* Formulário no lado direito */}
      <div className="bg-white text-gray-900 shadow-2xl rounded-2xl p-8 w-full max-w-sm">
        <h1 className="text-3xl font-bold text-yellow-600 mb-6 text-center">Bem-vindo à AntWeb</h1>
        <p className="text-gray-700 text-center mb-8">
          Preencha o formulário abaixo para que um consultor de vendas entre em contato com você.
        </p>

        <form onSubmit={handleSubmit} className="space-y-6">
          <div>
            <label htmlFor="nome" className="block text-sm font-medium text-gray-700">Nome completo</label>
            <input
              type="text"
              name="nome"
              id="nome"
              value={formData.nome}
              onChange={handleChange}
              required
              className="mt-1 block w-full px-4 py-2 border border-gray-300 rounded-md shadow-sm focus:ring-yellow-500 focus:border-yellow-500"
            />
          </div>

          <div>
            <label htmlFor="email" className="block text-sm font-medium text-gray-700">E-mail</label>
            <input
              type="email"
              name="email"
              id="email"
              value={formData.email}
              onChange={handleChange}
              required
              className="mt-1 block w-full px-4 py-2 border border-gray-300 rounded-md shadow-sm focus:ring-yellow-500 focus:border-yellow-500"
            />
          </div>

          <div>
            <label htmlFor="telefone" className="block text-sm font-medium text-gray-700">Telefone</label>
            <input
              type="tel"
              name="telefone"
              id="telefone"
              value={formData.telefone}
              onChange={handleChange}
              required
              className="mt-1 block w-full px-4 py-2 border border-gray-300 rounded-md shadow-sm focus:ring-yellow-500 focus:border-yellow-500"
            />
          </div>

          <button
            type="submit"
            className="w-full bg-yellow-500 text-white py-2 px-4 rounded-md hover:bg-yellow-600 transition-colors"
          >
            Enviar Cadastro
          </button>
        </form>
      </div>
    </div>
  );
}
