# Shibarium Token Bridge

This is the official repository for Shibarium token images and details, supporting the **Ethereum**, **Sepolia**, **Shibarium**, and **Puppynet** networks.

## Folder Structure

```
assets/
├── images/
│   ├── ethereum/
│   │   └── {tokenAddress}.png
│   ├── sepolia/
│   │   └── {tokenAddress}.png
│   ├── shibarium/
│   │   └── {tokenAddress}.png
│   └── puppynet/
│       └── {tokenAddress}.png
├── data/
│   ├── ethereum/
│   │   └── {tokenAddress}.json
│   ├── sepolia/
│   │   └── {tokenAddress}.json
│   ├── shibarium/
│   │   └── {tokenAddress}.json
│   └── puppynet/
│       └── {tokenAddress}.json
```

### Network Directories

- **Ethereum Network**
  - **Path**: `assets/images/ethereum/`, `assets/data/ethereum/`
  - **Description**: Contains images and details for tokens on the **Ethereum** network.

- **Shibarium Network**
  - **Path**: `assets/images/shibarium/`, `assets/data/shibarium/`
  - **Description**: Contains images and details for tokens on the **Shibarium** network.

- **Sepolia Network**
  - **Path**: `assets/images/sepolia/`, `assets/data/sepolia/`
  - **Description**: Contains images and details for tokens on the **Sepolia** test network.

- **Puppynet Network**
  - **Path**: `assets/images/puppynet/`, `assets/data/puppynet/`
  - **Description**: Contains images and details for tokens on the **Puppynet** test network.

---

## How to Add a New Token

### 1. Determine the Token Network

- Decide whether the token belongs to the **Ethereum**, **Sepolia**, **Shibarium**, or **Puppynet** network.

### 2. Add Token Image and JSON File

- For each token, create two files:
  1. **Token Image**: Place the token image inside the appropriate `images/{network}/` folder.
     - **File Naming**: Name the image file using the **token's address**, in lower case followed by `.png` (e.g., `0x1234567890abcdef.png`).
     - **File Size**: Ensure the image size does not exceed **200 KB**.
  2. **Token Details**: Add the token details in a JSON file inside the corresponding `data/{network}/` folder.
     - **File Naming**: Name the JSON file using the **token's address**, in lower case followed by `.json` (e.g., `0x1234567890abcdef.json`).

```json
{
    "parentName": "BONE SHIBASWAP",          // Name of the parent token (e.g., BONE SHIBASWAP)
    "parentSymbol": "BONE",                  // Symbol of the parent token (e.g., BONE)
    "parentContract": "0x9813037ee2218799597d83d4a5b6f3b6778218d9", // Address of the parent token contract
    "childName": "Bone Token",               // Name of the child token (e.g., Bone Token)
    "childSymbol": "BONE",                   // Symbol of the child token (e.g., BONE)
    "childContract": "0x0000000000000000000000000000000000001010", // Address of the child token contract
    "bridgeType": "plasma"  ,                 // Type of bridge (e.g., plasma, pos)
    "tokenWebsite": "https://example.com",    // Token Website
    "projectDescription": "A token built to enhance decentralized finance on the Shiba ecosystem.", // Brief description of the token project
    "contactInfo": "contact@example.com"      // Contact information for follow-up
}
```

### 3. Create a Pull Request (PR)

- Once you have added the image and `${tokenAddress}.json` file, **create a pull request (PR)** to the main branch with your changes.

### 4. PR Review and Approval

- Wait for the PR to be reviewed and approved by the maintainers.

---

## Image/Data URL Format

Once your PR is merged, the image for the token can be accessed via the following URL format:

```
https://cdn.shib.io/tokens/images/${chain}/${contractAddress.toLowerCase()}.png
```
```
https://cdn.shib.io/tokens/data/${chain}/${contractAddress.toLowerCase()}.json
```

- `${chain}`: Replace with the network (either `ethereum`, `sepolia`, `shibarium`, or `puppynet`).
- `${contractAddress}`: Use the **token's contract address** (in lowercase).


### Example URL:

If you added the `BONE` token for the **Ethereum** network, with the contract address `0x9813037ee2218799597d83d4a5b6f3b6778218d9`, the image URL would be:

```
https://cdn.shib.io/tokens/images/ethereum/0x9813037ee2218799597d83d4a5b6f3b6778218d9.png
```
```
https://cdn.shib.io/tokens/data/ethereum/0x9813037ee2218799597d83d4a5b6f3b6778218d9.json
```
---

## Contribution Guidelines

We welcome contributions! To ensure consistency and proper management of token images, please adhere to the following guidelines:

1. **Folder Naming**: Ensure the folder name is the **network** (e.g., `ethereum`, `sepolia`, `shibarium`, `puppynet`).
2. **Image Naming**: Name the image file using the **token address** in lower case followed by `.png` (e.g., `0x1234567890abcdef.png`).
3. **Image Size**: Ensure the token image does not exceed **200 KB** in size.
4. **File Format**: Use the specified structure for the `${tokenAddress}.json` in lower case.
5. **Contract Addresses**: Ensure that the contract addresses are accurate and in the correct format (all lowercase).

By following these instructions and ensuring the correctness of the files, your token addition will be quickly reviewed and integrated.