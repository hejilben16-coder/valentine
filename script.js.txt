const yesBtn = document.getElementById("yes");
const noBtn = document.getElementById("no");
const heartsContainer = document.querySelector(".hearts");

// YES → proposal page
yesBtn.addEventListener("click", () => {
  window.location.href = "proposal.html";
});

// NO → playful movement (no shrinking, no disappearing)
noBtn.addEventListener("mouseover", () => {
  const x = Math.random() * (window.innerWidth - 120);
  const y = Math.random() * (window.innerHeight - 120);
  noBtn.style.left = x + "px";
  noBtn.style.top = y + "px";
});

// Floating hearts & roses
const emojis = ["💖", "💕", "🌹", "❤️", "💘"];

function createHeart() {
  const span = document.createElement("span");
  span.innerHTML = emojis[Math.floor(Math.random() * emojis.length)];
  span.style.left = Math.random() * 100 + "vw";
  span.style.animationDuration = (6 + Math.random() * 4) + "s";
  heartsContainer.appendChild(span);

  setTimeout(() => span.remove(), 8000);
}

setInterval(createHeart, 400);
