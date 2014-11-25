encryptor
=========
class Encryptor


  def cipher(rotation)
    characters = (' '..'z').to_a
    rotated_characters = characters.rotate(rotation)
    Hash[characters.zip(rotated_characters)]
  end

  def encrypt_letter(letter,rotation)
    cipher_for_rotation = cipher(rotation)
    cipher_for_rotation[letter]
  end

  def encrypt(string, rotation)
    letters = string.split("")
    results = letters.collect { |letter| encrypt_letter(letter, rotation) }
    results.join
  end

end

JumpstartLab_encryptor_tutorial
