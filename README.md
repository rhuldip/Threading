# Threading
Process vs Thread
	- Process are heavy, Threads are lightweight.
	- Each process have a memory assigned which cant be shared between processes, while threads share same memory(other than thread local, and thread stack)
	- Inter process communication between processes are costly.
Creating Process in Java-
```
	public class ProcessExample {
		public static void main(String[] args) {
			ProcessBuilder processBuilder = new ProcessBuilder();
			
			// Configure the command to execute
			processBuilder.command("notepad.exe"); // Example: launching Notepad on Windows

			try {
				Process process = processBuilder.start(); // Start the new process
				System.out.println("Notepad started.");
				
				// Wait for the process to complete
				process.waitFor();
				
				System.out.println("Notepad terminated.");
			} catch (IOException | InterruptedException e) {
				e.printStackTrace();
			}
		}
	}
```
```
	public class RuntimeExample {
		public static void main(String[] args) {
			Runtime runtime = Runtime.getRuntime();
			try {
				Process process = runtime.exec("notepad.exe"); // Example: launching Notepad on Windows
				System.out.println("Notepad started.");
				
				// Optionally, wait for the process to complete
				process.waitFor();
				
				System.out.println("Notepad terminated.");
			} catch (IOException | InterruptedException e) {
				e.printStackTrace();
			}
		}
	}
```
Thread 
