# paranoiachargen
A script to generate characters for the first edition of the Paranoia RPG. 

## Requirements
* Python 3
* [Pillow](https://pypi.org/project/Pillow/) (`pip install Pillow`)
* The **Post Box Regular** font installed on the system (used to fill the printable sheet)

## Features
* Creates first edition Paranoia characters
* Assigns random names based on US census data
* Calculates all secondary attributes, and applies them to relevant skills
* Boosts attributes based on mutant powers or skills, where applicable
* Output fits nicely on a single page of letter paper, in 12pt monospace text
* **Renders a filled-in printable character sheet** (PDF or PNG) by drawing the
  generated character data directly onto the included `paranoia-sheet.png`
  template using the Post Box Regular font *(added by [creatorlars](https://github.com/creatorlars))*
* Multi-line areas (mutant powers, equipment, skills) are auto-laid-out into
  one, two, or three balanced columns and the font auto-shrinks to fit *(added by creatorlars)*
* Command-line interface with options to override the character name, choose
  the output path, emit the legacy text dump, or skip rendering *(added by creatorlars)*

## Usage
Run the character.py script. By default it generates a character and writes a
filled PDF sheet named after the character into the current directory:

    ./character.py

### Command-line options

| Option              | Description                                                          |
| ------------------- | -------------------------------------------------------------------- |
| `--name NAME`       | Override the randomly generated character name.                      |
| `--output PATH`     | Output path for the rendered sheet (`.pdf` or `.png`).               |
| `--text`            | Also print the original text dump to stdout.                         |
| `--no-sheet`        | Skip rendering the filled sheet (useful with `--text`).              |

Examples:

    # Generate a character and write Bob-R-XYZ-1.pdf
    ./character.py --name Bob-R-XYZ-1

    # Render to a specific PNG
    ./character.py --output sheet.png

    # Old-style text-only output, no PDF
    ./character.py --text --no-sheet > character_sheet.txt
        
## Sample Output

    NAME                Ike-R-VZQ-1
    
    PRIMARY ATTRIBUTES                      SECONDARY ATTRIBUTES
    Strength             12                 Carrying Capacity    25kg
    Endurance            15                 Damage Bonus          0
    Agility              15                 Macho Bonus          -1
    Manual Dexterity      9                 Melee Bonus         +10%
    Moxie                16                 Aimed Weapon Bonus   -2%
    Chutzpah             15                 Comprehension Bonus +10%
    Mechanical Aptitude   8                 Believability Bonus +10%
    Power Index          10                 Repair Bonus         -3%
    
    SECURITY CLEARANCE  RED
    SERVICE GROUP       Internal Security
    SECRET SOCIETY      Programs Group, rank 1
    
    MUTANT POWERS
    Superior Moxie (mental)
    
    CREDITS              45
    
    EQUIPMENT
    red reflec armor                        laser pistol
    laser barrel (red stripe)               jump suit
    utility belt & pouches                  Com Unit I
    knife                                   notebook & stylus
    SuperGum & solvent                      smoke alarm
    picture of Teela-O-MLY-1
    
    WEAPONS
    laser pistol         23%
    knife (melee)        35%
    knife (thrown)       23%
    
    SKILLS
    Basics (1) - 20%/20%
        Melee Combat (2) - 25%/35%
        Weapon Maintenance (2) - 25%/22%
        Special Services (2) - 25%/35%
        Aimed Weapon Combat (2) - 25%/23%
    Personal Development (1) - 20%/20%

## Limitations
* For simplicity's sake, plasticord is purchased in 25 feet increments, rather than 1 foot per the Player's Guide
* Will not assign treasonous skills - again, this is per the Player's Guide
* Skills aren't assigned "intelligently", so generated characters may have useless skills, or skills with very low secondary attribute bonuses

## Acknoweldgements
The rules for character creation, and all the tables used, originate in the Paranoia Player's Handbook, first edition, &copy; 1984 West End Games.

## License
This application is licensed under the GNU General Public License, version 3.

## Contributors
* Original author: [rjhelms](https://github.com/rjhelms)
* Printable character sheet rendering and CLI: [creatorlars](https://github.com/creatorlars)

## Contacts
* E-mail: <robhailman@gmail.com>
* Twitter: <https://twitter.com/rjhelms>