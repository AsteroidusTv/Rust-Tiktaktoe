fn main() {
    let win = [
        [0, 1, 2],
        [3, 4, 5],
        [6, 7, 8],
        [0, 3, 6],
        [1, 4, 7],
        [2, 5, 8],
        [0, 4, 8],
        [2, 4, 6],
    ];

    let mut current = vec![];
    let mut player1_list = vec![];
    let mut player2_list = vec![];
    let mut player = 2;

    loop {
        // Change the player at each iteration
        if player == 2 {
            player = 1;
        } else {
            player = 2;
        }

        // Retrieve the number of the user
        let mut x = ask_number();

        if player == 1 {
            loop {
                if current.contains(&x) {
                    println!("Élément déjà dans la liste");
                    x = ask_number()
                } else {
                    current.push(x);
                    player1_list.push(x);
                    break;
                }
            }

            println!("{:?}", current);

            for pattern in win.iter() {
                let mut match_count = 0;

                for &value in pattern.iter() {
                    if player1_list.contains(&value) {
                        match_count += 1;
                    }
                }

                if match_count == pattern.len() {
                    println!("Player 1 wins!");
                    return;
                }
            }
            println!("La liste de {} est {:?}", player, player1_list);
        } else {
            loop {
                if current.contains(&x) {
                    println!("Élément déjà dans la liste");
                    x = ask_number() // Ask for a new number
                } else {
                    current.push(x);
                    player2_list.push(x);
                    break;
                }
            }

            println!("{:?}", current);

            for pattern in win.iter() {
                let mut match_count = 0;

                for &value in pattern.iter() {
                    if player2_list.contains(&value) {
                        match_count += 1;
                    }
                }

                if match_count == pattern.len() {
                    println!("Player 2 wins!");
                    return;
                }
            }
            println!("La liste de {} est {:?}", player, player2_list);
        }
        println!("Le joueur est {}", player);
    }
}

// Ask a number from the user
fn ask_number() -> i32 {
    loop {
        let mut line = String::new();
        println!("Entrez un nombre (entre 0 et 8) :");
        std::io::stdin().read_line(&mut line).unwrap();
        let number: i32 = match line.trim().parse() {
            Ok(num) if (0..=8).contains(&num) => num,
            _ => {
                println!("Nombre invalide. Veuillez réessayer.");
                continue;
            }
        };
        return number; 
    }
}

