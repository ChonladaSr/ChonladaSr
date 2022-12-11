import 'dart:io';
import 'dart:math';

void main() {
  var r = Random();
  var answer = r.nextInt(31) + 20;

  int? guess;
  do {
    stdout.write('Guess the number between 1 and 100 : ');
    var input = stdin.readLineSync();
    if (input == null) {
      print('Error , input is null');
      return;
    }

    var guess = int.tryParse(input);
    if (guess == null) {
      print('Input error, please enter number only');
      return;
    }
    if (guess == answer) {
      print('Correct! The answer is $answer');
    } else if (guess > answer) {
      print('Too High');
    } else {
      print("Too Low");
    }
  } while (guess != answer);
}
