# Minigrep

Minigrep is a simple command-line tool written in Rust that mimics some of the basic functionality of the `grep` command. It allows users to search for a specified query string within a file and outputs the lines that contain the query. The tool supports case-sensitive and case-insensitive searches, making it a lightweight utility for text searching.

## Features
- Search for a query string in a specified file.
- Support for case-sensitive and case-insensitive searches.
- Simple and intuitive command-line interface.
- Built with Rust for performance and safety.

## Installation

To use Minigrep, you need to have Rust installed on your system. Follow these steps to set up and build the project:

1. **Install Rust**:
   If you don't have Rust installed, you can install it using `rustup`:
   ```bash
   curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh
   ```
   Follow the on-screen instructions to complete the installation. Ensure `cargo` is available in your terminal by running:
   ```bash
   cargo --version
   ```

2. **Clone the Repository**:
   Clone this repository to your local machine:
   ```bash
   git clone https://github.com/your-username/minigrep.git
   cd minigrep
   ```

3. **Build the Project**:
   Use Cargo to build the project:
   ```bash
   cargo build --release
   ```
   The executable will be located in `target/release/minigrep`.

4. **Run the Project**:
   You can run Minigrep directly using Cargo:
   ```bash
   cargo run -- [QUERY] [FILE_PATH]
   ```
   Alternatively, use the compiled binary:
   ```bash
   ./target/release/minigrep [QUERY] [FILE_PATH]
   ```

## Usage

Minigrep takes two main arguments: a query string and a file path. By default, the search is case-sensitive. To perform a case-insensitive search, set the `IGNORE_CASE` environment variable.

### Basic Command
Search for a query in a file:
```bash
cargo run -- to poem.txt
```
This searches for the word "to" in `poem.txt` and prints all lines containing the query.

### Case-Insensitive Search
To ignore case during the search:
```bash
IGNORE_CASE=1 cargo run -- to poem.txt
```
This will match "to", "To", "TO", etc.

### Example
Given a file `poem.txt` with the following content:
```
I'm nobody! Who are you?
Are you nobody, too?
Then there's a pair of us - don't tell!
They'd banish us, you know.
```

Running:
```bash
cargo run -- nobody poem.txt
```
Outputs:
```
I'm nobody! Who are you?
Are you nobody, too?
```

Running with case-insensitive search:
```bash
IGNORE_CASE=1 cargo run -- NOBODY poem.txt
```
Outputs the same result as above.

### Help
To see the help message:
```bash
cargo run -- --help
```
This displays usage information and available options.

## Project Structure
- `src/main.rs`: The main entry point of the application.
- `src/lib.rs`: Contains the core logic for parsing arguments and performing the search.
- `tests/`: Directory containing unit and integration tests.

## Testing
Run the tests to ensure the application works as expected:
```bash
cargo test
```
This executes all unit and integration tests defined in the project.

## Contributing
Contributions are welcome! To contribute:
1. Fork the repository.
2. Create a new branch (`git checkout -b feature/your-feature`).
3. Make your changes and commit them (`git commit -m "Add your feature"`).
4. Push to the branch (`git push origin feature/your-feature`).
5. Open a pull request.

Please ensure your code follows Rust's coding conventions (run `cargo fmt`) and includes tests for new functionality.

## License
This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

## Acknowledgments
This project was inspired by the ["Command Line Program" chapter](https://doc.rust-lang.org/book/ch12-00-an-io-project.html) in *The Rust Programming Language* book.