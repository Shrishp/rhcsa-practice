How to Reset Root Password in RHEL 9 (VM/Server)
Recently, I explored how to reset the root password on a RHEL 9 system — a crucial recovery task for any Linux user or system administrator.

This hands-on experience helped me understand the GRUB boot process, emergency mode, and SELinux relabeling. It’s fascinating to see how Linux offers robust mechanisms for system recovery, and I’m excited to keep learning more!

Restart or Start the VM: Reboot or power on your virtual machine.
Enter GRUB Menu: Press the ↑↓ arrow keys rapidly during boot to access the GRUB menu.
Select Rescue Kernel: Highlight the rescue kernel using the arrow keys, then press e to edit.
![image](https://github.com/user-attachments/assets/0a6d041c-66e8-47d8-b6bc-822e04a04456)
4. Modify Linux Line: Locate the line that starts with ‘linux’. Replace ro (read-only) with rw (read-write) and append rd.break console=tty0 to pause the boot process for recovery.
![image](https://github.com/user-attachments/assets/e92395fd-965b-4698-ba0a-3bbfa3365b67)
![image](https://github.com/user-attachments/assets/6c10aacc-d2f3-44ec-9ef2-b9169c47a0c2)
5. Boot into Rescue Mode: Press Ctrl+X to boot with the edited settings.

6. Access System Root: Run chroot /sysroot to switch to the system’s root environment.
![image](https://github.com/user-attachments/assets/62d431c3-3218-4df0-94a6-027faa5b17fc)
7. Reset Root Password: Execute passwd root and enter a new password when prompted.
![image](https://github.com/user-attachments/assets/c002c3e0-97a6-4e96-b9a6-ba8ca4a86871)
8. Enable SELinux Relabeling: Run touch /.autorelabel to update SELinux contexts on reboot.
![image](https://github.com/user-attachments/assets/facb1cfc-129d-4119-b644-647ed8510f77)
9. Exit and Reboot: Type exit twice to leave chroot and restart the system.

This process has sharpened my Linux troubleshooting skills, and I’m excited to share it! Try it out, share your tips in the comments, or pass it along to your network. 🚀

