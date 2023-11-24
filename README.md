Installation de pytest
Pour installer pytest, exécutez la commande suivante dans votre terminal ou votre invite de commande :

bash
Copy code
pip install -U pytest
Vérification de la version installée
Pour vérifier que pytest est correctement installé et connaître la version, utilisez la commande suivante :

bash
Copy code
pytest --version
Création d'un premier test
Créez un nouveau fichier appelé test_sample.py avec le contenu suivant :

python
Copy code
# content of test_sample.py
def func(x):
    return x + 1

def test_answer():
    assert func(3) == 5
Ce test compare le résultat de func(3) avec 5, ce qui générera une assertion qui échouera lors de l'exécution.

Exécution des tests
Exécutez les tests en utilisant la commande suivante dans le répertoire où se trouve le fichier de test :

bash
Copy code
pytest
Vous devriez voir un résultat semblable à celui que vous avez partagé, indiquant qu'un test a échoué.

Lever une exception dans un test
Créez un fichier appelé test_sysexit.py avec le contenu suivant :

python
Copy code
import pytest

def f():
    raise SystemExit(1)

def test_mytest():
    with pytest.raises(SystemExit):
        f()
Ce test vérifie si la fonction f déclenche une exception SystemExit.

Regrouper plusieurs tests dans une classe
Créez un fichier appelé test_class.py avec le contenu suivant :

python
Copy code
class TestClass:
    def test_one(self):
        x = "this"
        assert "h" in x

    def test_two(self):
        x = "hello"
        assert hasattr(x, "check")
Ici, nous avons deux tests dans une classe TestClass. Le premier test vérifie si la lettre "h" est présente dans la chaîne, et le deuxième teste si la chaîne a l'attribut "check".

Demander un répertoire temporaire unique pour les tests fonctionnels
Créez un fichier appelé test_tmp_path.py avec le contenu suivant :

python
Copy code
def test_needsfiles(tmp_path):
    print(tmp_path)
    assert 0
Ce test utilise le répertoire temporaire fourni par pytest. Le paramètre tmp_path est automatiquement découvert et fourni par pytest.

Exécutez les tests avec la commande :

bash
Copy code
pytest -q test_tmp_path.py
Vous devriez voir un résultat indiquant que le test a échoué, mais le répertoire temporaire utilisé sera imprimé.

Ces exemples devraient vous donner une idée de la manière d'écrire et d'exécuter des tests avec pytest. Si vous avez des questions spécifiques sur l'un de ces exemples ou si vous souhaitez explorer davantage, n'hésitez pas à demander !




