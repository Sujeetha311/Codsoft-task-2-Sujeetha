import java.util.Scanner;
import java.util.Random;

class Task2_NumberGame {
    public static void main(String[] args) {
        Scanner kb = new Scanner(System.in);
        Random findRandom = new Random();

        // 🌟 Stylish Header
        System.out.println("╔══════════════════════════════════════════════════════════════╗");
        System.out.println("║                    🎮 CodSoft Internship Program             ║");
        System.out.println("║                        🕹️ Task 2: Number Game               ║");
        System.out.println("╠══════════════════════════════════════════════════════════════╣");
        System.out.println("║ 👩‍💻 Developer : Sujeetha                                    ║");
        System.out.println("║ 🎓 College   : Rajalakshmi Institute of Technology           ║");
        System.out.println("║ 🏢 Company   : CodSoft                                       ║");
        System.out.println("╚══════════════════════════════════════════════════════════════╝\n");

        // 🎯 Game Setup
        System.out.println("🎯 Create a random number with specified range:");
        System.out.print("📥 Enter Lower Limit: ");
        int lowerLimit = kb.nextInt();

        System.out.print("📥 Enter Upper Limit: ");
        int upperLimit = kb.nextInt();

        int range = upperLimit - lowerLimit;
        int target = findRandom.nextInt(range + 1) + lowerLimit;

        int guess, maxAttempts = 5, maxScore = 0;

        // 📜 Instructions
        System.out.println("\n📜 Game Instructions:");
        System.out.println("1️⃣ You have 5 chances to guess the number.");
        System.out.println("2️⃣ Each correct guess earns you more points.");
        System.out.println("3️⃣ Early guess = Higher score (Max 100).");
        System.out.println("4️⃣ Miss all attempts = Score 0.");

        System.out.println("\n🎮 Welcome to the Number Game! Let’s Begin 🎯");

        // 🎲 Game Loop
        for (int chance = 1; chance <= maxAttempts; chance++) {
            System.out.print("➡️ Attempt " + chance + ": Guess a number: ");
            guess = kb.nextInt();

            if (guess < target) {
                System.out.println("📉 Too low!");
            } else if (guess > target) {
                System.out.println("📈 Too high!");
            } else {
                maxScore = (maxAttempts - chance + 1) * 20;
                System.out.println("🎉 Congratulations! You found the number!");
                System.out.println("🏆 Your Score: " + maxScore + " / 100");
                break;
            }

            if (chance == maxAttempts) {
                System.out.println("❌ CHANCES OVER – You failed to guess the number!");
                System.out.println("😢 Your Score: 0 / 100");
                System.out.println("🎯 The correct number was: " + target);
            }
        }

        // 🎉 Stylish Footer
        System.out.println("\n╔══════════════════════════════════════════════════════╗");
        System.out.println("║ ✅ Task 2 Completed Successfully                     ║");
        System.out.println("║ 👩‍💻 Submitted by: Sujeetha                         ║");
        System.out.println("║ 🎓 Rajalakshmi Institute of Technology              ║");
        System.out.println("║ 🚀 Internship by: CodSoft                           ║");
        System.out.println("╚══════════════════════════════════════════════════════╝");

        kb.close();
    }
}
