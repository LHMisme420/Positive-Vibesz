# Positive-Vibesz
Uplifting memes
import matplotlib.pyplot as plt
import matplotlib.patches as patches
import random
import time
import argparse
from datetime import datetime

# Positive vibes bank: Mix of quotes, affirmations, and fun facts
POSITIVE_CONTENT = [
    "You are capable of amazing things. Today, prove it to yourself.",
    "Small steps lead to big leaps. What's your next one?",
    "Kindness is free—sprinkle it everywhere.",
    "Fun fact: Laughter boosts your immune system. Giggle on!",
    "Breathe in peace, exhale doubt. You've got this.",
    "Every sunrise is nature's way of saying 'Let's try again.'",
    "You're not a drop in the ocean; you're the entire ocean in a drop.",
    "Celebrate the wins, no matter how tiny. High-five incoming!",
    "Curiosity is your superpower. What will you discover today?",
    "Rest is progress. Pause and recharge like a boss."
]

def generate_meme():
    # Pick a random positive message
    message = random.choice(POSITIVE_CONTENT)
    
    # Create a simple uplifting background (gradient-like with color blocks)
    fig, ax = plt.subplots(1, 1, figsize=(8, 6))
    ax.set_xlim(0, 8)
    ax.set_ylim(0, 6)
    ax.axis('off')
    
    # Add colorful, positive blocks (sunny vibes)
    colors = ['#FFD700', '#FFA500', '#FF69B4', '#98FB98']  # Gold, orange, hot pink, pale green
    for i in range(4):
        rect = patches.Rectangle((i*2, 0), 2, 6, linewidth=0, facecolor=colors[i])
        ax.add_patch(rect)
    
    # Overlay the message in bold, centered text
    ax.text(4, 3, message, ha='center', va='center', fontsize=14, fontweight='bold',
            wrap=True, color='white', bbox=dict(boxstyle="round,pad=0.5", facecolor='black', alpha=0.7))
    
    # Timestamp for that "freshly baked" feel
    timestamp = datetime.now().strftime("%Y-%m-%d %H:%M")
    ax.text(4, 0.5, f"Generated with positivity at {timestamp}", ha='center', va='center',
            fontsize=8, style='italic', color='white')
    
    # Save as PNG
    filename = f"uplift_meme_{datetime.now().strftime('%Y%m%d_%H%M%S')}.png"
    plt.savefig(filename, bbox_inches='tight', dpi=150, facecolor='none', edgecolor='none')
    plt.close()
    
    print(f"✨ Fresh meme dropped: {filename} ✨")
    print(f"Message: {message}")

def main():
    parser = argparse.ArgumentParser(description="Positive Meme Generator")
    parser.add_argument('--single', action='store_true', help="Generate one meme and exit")
    parser.add_argument('--interval', type=int, default=3600, help="Seconds between generations (default: 1 hour)")
    args = parser.parse_args()
    
    if args.single:
        generate_meme()
    else:
        print("🚀 Positive Meme Generator starting... Generating every", args.interval, "seconds (Ctrl+C to stop).")
        try:
            while True:
                generate_meme()
                time.sleep(args.interval)
        except KeyboardInterrupt:
            print("\n🌟 Loop paused. You've spread enough joy for now!")

if __name__ == "__main__":
    main()
POSITIVE_CONTENT = [
    # Original entries (Keeping for context)
    "You are capable of amazing things. Today, prove it to yourself.",
    "Small steps lead to big leaps. What's your next one?",
    "Kindness is free—sprinkle it everywhere.",
    "Fun fact: Laughter boosts your immune system. Giggle on!",
    "Breathe in peace, exhale doubt. You've got this.",
    "Every sunrise is nature's way of saying 'Let's try again.'",
    "You're not a drop in the ocean; you're the entire ocean in a drop.",
    "Celebrate the wins, no matter how tiny. High-five incoming!",
    "Curiosity is your superpower. What will you discover today?",
    "Rest is progress. Pause and recharge like a boss.",
    
    # NEW Entries to add 🚀
    "Don't wait for permission to shine. Your light is ready now!",  # Motivation
    "Gratitude turns what we have into enough. Name three things you're thankful for.",  # Gratitude
    "Fun fact: Honey never spoils. Your potential is just as timeless.",  # Fun Fact/Analogy
    "The world needs your unique blend of magic. Don't dim it down.",  # Self-Acceptance
    "A mistake is just proof that you are trying. Keep learning, keep going.",  # Resilience
    "Treat yourself like someone you love. You deserve the best care.",  # Self-Care
    "Today's good mood is sponsored by coffee and your amazing attitude.",  # Lighthearted
    "Imagine the best-case scenario. Now, go make it happen.",  # Visualization
    "Your presence is a gift. The people around you are lucky to have you.",  # Affirmation
    "Fun fact: A single cloud can weigh over a million pounds. You can carry your day!",  # Fun Fact/Strength
]
