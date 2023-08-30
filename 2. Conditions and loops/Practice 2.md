# Practice 2
แบบฝึกหัดในเรื่อง Conditions and loops
# 1.Write a dart program to check if the number is odd or even.
    
    โปรแกรมการเช็คเลขคู่หรือเลขคี่ในภาษา Dart
    
      void main() {
        int number = 7; สามารถเปลี่ยนเลขเพื่อเช็คได้
        if (number % 2 == 0) {
            print('$number is even');
        } else {
            print('$number is odd');
        }
      }

    โปรแกรมการเช็คเลขคู่หรือเลขคี่ในภาษา C
    
    #include <stdio.h>
    int main() {
      int number = 7; สามารถเปลี่ยนเลขเพื่อเช็คได้
      if (number % 2 == 0) {
          printf("%d is even\n", number);
      } else {
          printf("%d is odd\n", number);
      }
      return 0;
    }

    โปรแกรมการเช็คเลขคู่หรือเลขคี่ในภาษา Java
    public class OddEvenCheck {
      public static void main(String[] args) {
        int number = 7; สามารถเปลี่ยนเลขเพื่อเช็คได้
        if (number % 2 == 0) {
            System.out.println(number + " is even");
        } else {
            System.out.println(number + " is odd");
        }
      }
    }

    โปรแกรมการเช็คเลขคู่หรือเลขคี่ในภาษา Python
    number = 7  สามารถเปลี่ยนเลขเพื่อเช็คได้
    if number % 2 == 0:
      print(f'{number} is even')
    else:
      print(f'{number} is odd')
    
# 2.Write a dart program to check whether a character is a vowel or consonant.
    
    โปรแกรมการเช็คว่าเป็นสระหรือพยัญชนะในภาษา Dart
    void main() {
        String character = 'a'; สามารถเปลี่ยนอักขระเพื่อเช็คได้
        if ('aeiouAEIOU'.contains(character)) {
            print('$character is a vowel');
        } else {
            print('$character is a consonant');
        }
    }
    
    โปรแกรมการเช็คว่าเป็นสระหรือพยัญชนะในภาษา C
    #include <stdio.h>
  
    int main() {
        char character = 'a'; // สามารถเปลี่ยนอักขระเพื่อเช็คได้
        if (character == 'a' || character == 'e' || character == 'i' || character == 'o' || character == 'u' ||
            character == 'A' || character == 'E' || character == 'I' || character == 'O' || character == 'U') {
            printf("%c is a vowel\n", character);
        } else {
            printf("%c is a consonant\n", character);
        }
        return 0;
    }
    
    โปรแกรมการเช็คว่าเป็นสระหรือพยัญชนะในภาษา Java
    public class VowelConsonantCheck {
        public static void main(String[] args) {
            char character = 'a'; สามารถเปลี่ยนอักขระเพื่อเช็คได้
            if ("aeiouAEIOU".contains(Character.toString(character))) {
                System.out.println(character + " is a vowel");
            } else {
                System.out.println(character + " is a consonant");
            }
        }
    }
    
    โปรแกรมการเช็คว่าเป็นสระหรือพยัญชนะในภาษา Python
		character = 'a'  # Change this value to the character you want to check
    if character.lower() in 'aeiou':
        print(f'{character} is a vowel')
    else:
        print(f'{character} is a consonant')

    
  
# 3.Write a dart program to check whether a number is positive, negative, or zero.

# 4.Write a dart program to print your name 100 times.

# 5.Write a dart program to calculate the sum of natural numbers.

# 6.Write a dart program to generate multiplication tables of 5.

# 7.Write a dart program to generate multiplication tables of 1-9.

# 8.Write a dart program to create a simple calculator that performs addition, subtraction, multiplication, and division.

# 9.Write a dart program to print 1 to 100 but not 41.
