// src/pages/Index.tsx
import React, { useEffect, useState } from "react";
import { StatusBar } from "@/components/landing/StatusBar";
import { Logo } from "@/components/landing/Logo";
import { Title } from "@/components/landing/Title";
import { ContinueButton } from "@/components/landing/ContinueButton";
import { AccessibilityIcon } from "@/components/landing/AccessibilityIcon";
import { SignInWindow } from "@/components/auth/SignInWindow";

const Index = () => {
  const [showContent, setShowContent] = useState(false);
  const [showSignIn, setShowSignIn] = useState(false);

  useEffect(() => {
    setTimeout(() => {
      setShowContent(true);
    }, 800);
  }, []);

  const handleContinue = () => {
    setShowSignIn(true);
  };

  return (
    <main className="w-full h-screen relative bg-gradient-to-b from-[#02358C] via-[#0353AC] to-[#0464bf]">
      <div className="absolute inset-0 bg-gradient-to-tr from-[#02358C]/90 via-[#0464bf]/80 to-[#E03A0A]/20 z-0"></div>
      <StatusBar />
      <div className="relative z-10 flex flex-col items-center justify-center h-full px-[31px] py-0 max-md:px-5 max-md:py-0 max-sm:px-4 max-sm:py-0">
        <div className="flex flex-col items-center space-y-5">
          <Logo
            src="https://cdn.builder.io/api/v1/image/assets/TEMP/2f58c6f70036d39c148cbaec4da3828732460c47"
            alt="Super Duper logo"
          />
          <Title>EL NUEVO CONCEPTO DE LO FRITO</Title>
          
          <div className={`flex flex-col items-center mt-24 max-sm:mt-20 transition-all duration-700 ease-out transform ${
            showContent ? "translate-y-0 opacity-100" : "translate-y-8 opacity-0"
          }`}>
            <div className="text-white text-[28px] font-light mb-6">
              Empecemos!
            </div>
            <ContinueButton onClick={handleContinue} />
          </div>
        </div>
        
        <AccessibilityIcon />
      </div>
      
      <div className="absolute bottom-0 left-0 w-32 h-32 rounded-full bg-gradient-to-tr from-[#E03A0A]/30 to-[#FF6A39]/20 blur-xl"></div>
      <div className="absolute top-1/4 right-0 w-32 h-32 rounded-full bg-gradient-to-bl from-[#0353AC]/20 to-[#02358C]/10 blur-xl"></div>
      <div className="absolute bottom-1/3 right-1/4 w-24 h-24 rounded-full bg-gradient-to-r from-[#FF6A39]/10 to-[#FFA07A]/10 blur-xl"></div>
      
      <SignInWindow isOpen={showSignIn} onClose={() => setShowSignIn(false)} />
    </main>
  );
};

export default Index;
