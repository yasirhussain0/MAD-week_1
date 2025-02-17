# MAD-week_1









void main() {
  String text = '''
This is a really really cool experiment really
cute little experiment
will it work maybe it will work do you think it will it will
''';

  List<String> rows = text.split('\n');

  for (int i = 0; i < rows.length; i++) {
    String row = rows[i].trim();
    if (row.isEmpty) continue;

    List<String> words = row.toLowerCase().split(' ');

    Map<String, int> wordCount = {};
    for (int j = 0; j < words.length; j++) {
      String word = words[j];
      if (wordCount.containsKey(word)) {
        wordCount[word] = wordCount[word]! + 1;
      } else {
        wordCount[word] = 1;
      }
    }

    bool hasRepeats = false;
    print('sentence ${i + 1}:');
    for (String word in wordCount.keys) {
      if (wordCount[word]! > 1) {
        print('  "$word" repeats ${wordCount[word]} times');
        hasRepeats = true;
      }
    }

    if (!hasRepeats) {
      print('  This sentence has a frequency of 1');
    }
  }
}
