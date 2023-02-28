4public class VegenereCipher
{
    public class VegenereCipher
    {
        private String key;
        private String alphabet;

        public VegenereCipher(String key)
        {
            this.key = key;
            this.alphabet = "abcdefghijklmnopqrstuvwxyzABCDEFGHIJKLMNOPQRSTUVWXYZ";
        }

        public String getKey()
        {
            return key.toLowerCase();
        }
        public String getAlphabet()
        {
        return alphabet;
        }

        public void setKey(String key)
        {
            this.key = key;
        }


        public String encode(String input)
        {
            String keyAtLength = keyLength(input);
            String lowerCaseInput = input.toLowerCase();
            String encoded = "";
            for(int i = 0; i < input.length(); i++)
            {
                int checkIfLetterExist = input.charAt(i);
                if (checkIfLetterExist < 97 || checkIfLetterExist > 122)
                {
                    encoded += input.charAt(i);
                }
                else
                {
                    int inputAscii = lowerCaseInput.charAt(i);
                    int keyAscii = keyAtLength.charAt(i);
                    int difference = inputAscii - 97;
                    int keyNewValue = keyAscii + difference;
                    if (keyNewValue > 122)
                    {
                        difference = keyNewValue - 122;
                        keyNewValue = difference + 96;
                        char encodedLetter = (char) keyNewValue;
                        encoded += encodedLetter;
                    }
                    else
                    {
                        char encodedLetter = (char) keyNewValue;
                        encoded += encodedLetter;
                    }
                }
            }
            return encoded;
        }
        public String decode(String input)
        {
            String keyAtLength = keyLength(input);
            String lowerCaseInput = input.toLowerCase();
            String decoded = "";
            for(int i = 0; i < input.length(); i++)
            {
                int checkIfLetterExist = input.charAt(i);
                if (checkIfLetterExist < 97 || checkIfLetterExist > 122)
                {
                    decoded += input.charAt(i);
                }
                else
                {
                    int inputAscii = lowerCaseInput.charAt(i);
                    int keyAscii = keyAtLength.charAt(i);
                    int difference = inputAscii - keyAscii;
                    int keyNewValue = 0;
                    if (difference < 0)
                    {
                        keyNewValue = difference + 123;
                        char decodedLetter = (char) keyNewValue;
                        decoded += decodedLetter;
                    }
                    else
                    {
                        keyNewValue = difference + 97;
                        char decodedLetter = (char) keyNewValue;
                        decoded += decodedLetter;
                    }
                }
            }

            return decoded;
        }
        public String keyLength(String input)
        {
            String keyAtLength = "";
            int keyIndex = 0;
            for(int i = 0; i < input.length(); i++)
            {
                keyAtLength += key.charAt(keyIndex);
                keyIndex++;
                if(keyIndex == key.length())
                    keyIndex = 0;
            }
            keyAtLength = keyAtLength.toLowerCase();
            return keyAtLength;
        }


    }
}
