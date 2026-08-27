# Phone2PC

A browser-to-browser file-transfer app. The receiver opens the site on a computer, scans the generated QR code from a phone, and files are sent directly between the two browsers using WebRTC (PeerJS). Files are held only in the open receiver browser; there is no account, database, or cloud file storage.

## Publish it

1. Create a GitHub repository and upload `index.html` and this README.
2. Deploy it with GitHub Pages, Netlify, or Vercel.
3. Open the deployed HTTPS address on the computer. Scan the QR code with the phone.

Do **not** open it directly as a downloaded file (`file:///...`), because a phone cannot reach files stored on the computer. Both devices need internet access and the computer must keep the receiver page open.

## Included safeguards

- A fresh random receiver room for every session
- QR link points only to that temporary receiver room
- Automatic 30-minute room expiry
- 500 MB file limit per file
- Files are transferred directly to the receiver browser and disappear when the tab/session ends
- ZIP download and individual downloads

## Important operational note

This is a real direct-transfer implementation, not a mock upload screen. The PeerJS public signaling service establishes the browser connection. For a production government or high-volume deployment, use a managed PeerJS/TURN service and add a server-side relay/storage fallback for restrictive networks or very large files.
