# HTTP Toolkit Pro Patcher  
Get HTTP Toolkit Pro version for free  
### A simple patcher to enable Pro features in HTTP Toolkit

## Requirements  
- Node.js 15 or higher
- HTTP Toolkit installed

## Usage  
Installation and patch:
```bash
git clone https://github.com/thebadinteger/httptoolkit-patcher.git
cd httptoolkit-patcher
npm install
node . patch
```
Starting HTTP Toolkit:  
```bash
node . start
```
Restoring original (if needed): 
```bash
node . restore
```
Specify a custom install path:  
```bash
node . patch --path "C:\Program Files\HTTP Toolkit"
```
Linux / macOS may need elevate:  
```bash
sudo node . patch
sudo node . patch --path "/opt/HTTP Toolkit"
```
Works on Windows, macOS, and Linux  
Install locations are auto-detected on each platform; use `--path` to point at a non-default location  

## How it works  
1. Extracts the app.asar from HTTP Toolkit
2. Injects a local proxy server that intercepts UI requests
3. Patches the subscription data on-the-fly to enable Pro features
4. Flips Electron fuses to bypass ASAR integrity checks
5. Repacks the app

## Notes  
- Creates a backup at `app.asar.bak` (and `httptoolkit-server/bundle/index.js.bak`) before patching
- You can set a custom proxy with the `PROXY` environment variable
- Use `--path` to point at a non-default install location; auto-detection covers `Program Files` and the newer `Programs\httptoolkit\HTTP Toolkit` layout on Windows, `/Applications/HTTP Toolkit.app` on macOS, and `/opt`, `/usr/lib`, `/usr/share` locations on Linux
- Works offline after first run (caches UI files locally)

## License  
MIT

## Disclaimer  
Please buy [the original license](https://httptoolkit.com/), the program is only for educational purposes  

## Thanks  
Original by [@XielQ](https://github.com/XielQs), some updates by [@ayyo42069](https://github.com/ayyo42069)
