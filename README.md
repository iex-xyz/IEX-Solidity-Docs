#### Dispatch Admin - https://polygonscan.com/address/0xD68fAD6167c7573891c93c022772E9928A23464c#code
#### Dispatch Messenger - https://polygonscan.com/address/0xd6a4dF9E585318281e01AAcb125b7b488174cD35#code

# Solidity API

## Ownable

_Contract module which provides a basic access control mechanism, where
there is an account (an owner) that can be granted exclusive access to
specific functions.

By default, the owner account will be the one that deploys the contract. This
can later be changed with {transferOwnership}.

This module is used through inheritance. It will make available the modifier
`onlyOwner`, which can be applied to your functions to restrict their use to
the owner._

### _owner

```solidity
address _owner
```

### OwnershipTransferred

```solidity
event OwnershipTransferred(address previousOwner, address newOwner)
```

### constructor

```solidity
constructor() internal
```

_Initializes the contract setting the deployer as the initial owner._

### owner

```solidity
function owner() public view virtual returns (address)
```

_Returns the address of the current owner._

### onlyOwner

```solidity
modifier onlyOwner()
```

_Throws if called by any account other than the owner._

### renounceOwnership

```solidity
function renounceOwnership() public virtual
```

_Leaves the contract without owner. It will not be possible to call
`onlyOwner` functions anymore. Can only be called by the current owner.

NOTE: Renouncing ownership will leave the contract without an owner,
thereby removing any functionality that is only available to the owner._

### transferOwnership

```solidity
function transferOwnership(address newOwner) public virtual
```

_Transfers ownership of the contract to a new account (`newOwner`).
Can only be called by the current owner._

### _transferOwnership

```solidity
function _transferOwnership(address newOwner) internal virtual
```

_Transfers ownership of the contract to a new account (`newOwner`).
Internal function without access restriction._

## ERC1155

_Implementation of the basic standard multi-token.
See https://eips.ethereum.org/EIPS/eip-1155
Originally based on code by Enjin: https://github.com/enjin/erc-1155

_Available since v3.1.__

### _balances

```solidity
mapping(uint256 => mapping(address => uint256)) _balances
```

### _operatorApprovals

```solidity
mapping(address => mapping(address => bool)) _operatorApprovals
```

### _uri

```solidity
string _uri
```

### constructor

```solidity
constructor(string uri_) public
```

_See {_setURI}._

### supportsInterface

```solidity
function supportsInterface(bytes4 interfaceId) public view virtual returns (bool)
```

_See {IERC165-supportsInterface}._

### uri

```solidity
function uri(uint256) public view virtual returns (string)
```

_See {IERC1155MetadataURI-uri}.

This implementation returns the same URI for *all* token types. It relies
on the token type ID substitution mechanism
https://eips.ethereum.org/EIPS/eip-1155#metadata[defined in the EIP].

Clients calling this function must replace the `\{id\}` substring with the
actual token type ID._

### balanceOf

```solidity
function balanceOf(address account, uint256 id) public view virtual returns (uint256)
```

_See {IERC1155-balanceOf}.

Requirements:

- `account` cannot be the zero address._

### balanceOfBatch

```solidity
function balanceOfBatch(address[] accounts, uint256[] ids) public view virtual returns (uint256[])
```

_See {IERC1155-balanceOfBatch}.

Requirements:

- `accounts` and `ids` must have the same length._

### setApprovalForAll

```solidity
function setApprovalForAll(address operator, bool approved) public virtual
```

_See {IERC1155-setApprovalForAll}._

### isApprovedForAll

```solidity
function isApprovedForAll(address account, address operator) public view virtual returns (bool)
```

_See {IERC1155-isApprovedForAll}._

### safeTransferFrom

```solidity
function safeTransferFrom(address from, address to, uint256 id, uint256 amount, bytes data) public virtual
```

_See {IERC1155-safeTransferFrom}._

### safeBatchTransferFrom

```solidity
function safeBatchTransferFrom(address from, address to, uint256[] ids, uint256[] amounts, bytes data) public virtual
```

_See {IERC1155-safeBatchTransferFrom}._

### _safeTransferFrom

```solidity
function _safeTransferFrom(address from, address to, uint256 id, uint256 amount, bytes data) internal virtual
```

_Transfers `amount` tokens of token type `id` from `from` to `to`.

Emits a {TransferSingle} event.

Requirements:

- `to` cannot be the zero address.
- `from` must have a balance of tokens of type `id` of at least `amount`.
- If `to` refers to a smart contract, it must implement {IERC1155Receiver-onERC1155Received} and return the
acceptance magic value._

### _safeBatchTransferFrom

```solidity
function _safeBatchTransferFrom(address from, address to, uint256[] ids, uint256[] amounts, bytes data) internal virtual
```

_xref:ROOT:erc1155.adoc#batch-operations[Batched] version of {_safeTransferFrom}.

Emits a {TransferBatch} event.

Requirements:

- If `to` refers to a smart contract, it must implement {IERC1155Receiver-onERC1155BatchReceived} and return the
acceptance magic value._

### _setURI

```solidity
function _setURI(string newuri) internal virtual
```

_Sets a new URI for all token types, by relying on the token type ID
substitution mechanism
https://eips.ethereum.org/EIPS/eip-1155#metadata[defined in the EIP].

By this mechanism, any occurrence of the `\{id\}` substring in either the
URI or any of the amounts in the JSON file at said URI will be replaced by
clients with the token type ID.

For example, the `https://token-cdn-domain/\{id\}.json` URI would be
interpreted by clients as
`https://token-cdn-domain/000000000000000000000000000000000000000000000000000000000004cce0.json`
for token type ID 0x4cce0.

See {uri}.

Because these URIs cannot be meaningfully represented by the {URI} event,
this function emits no events._

### _mint

```solidity
function _mint(address to, uint256 id, uint256 amount, bytes data) internal virtual
```

_Creates `amount` tokens of token type `id`, and assigns them to `to`.

Emits a {TransferSingle} event.

Requirements:

- `to` cannot be the zero address.
- If `to` refers to a smart contract, it must implement {IERC1155Receiver-onERC1155Received} and return the
acceptance magic value._

### _mintBatch

```solidity
function _mintBatch(address to, uint256[] ids, uint256[] amounts, bytes data) internal virtual
```

_xref:ROOT:erc1155.adoc#batch-operations[Batched] version of {_mint}.

Requirements:

- `ids` and `amounts` must have the same length.
- If `to` refers to a smart contract, it must implement {IERC1155Receiver-onERC1155BatchReceived} and return the
acceptance magic value._

### _burn

```solidity
function _burn(address from, uint256 id, uint256 amount) internal virtual
```

_Destroys `amount` tokens of token type `id` from `from`

Requirements:

- `from` cannot be the zero address.
- `from` must have at least `amount` tokens of token type `id`._

### _burnBatch

```solidity
function _burnBatch(address from, uint256[] ids, uint256[] amounts) internal virtual
```

_xref:ROOT:erc1155.adoc#batch-operations[Batched] version of {_burn}.

Requirements:

- `ids` and `amounts` must have the same length._

### _setApprovalForAll

```solidity
function _setApprovalForAll(address owner, address operator, bool approved) internal virtual
```

_Approve `operator` to operate on all of `owner` tokens

Emits a {ApprovalForAll} event._

### _beforeTokenTransfer

```solidity
function _beforeTokenTransfer(address operator, address from, address to, uint256[] ids, uint256[] amounts, bytes data) internal virtual
```

_Hook that is called before any token transfer. This includes minting
and burning, as well as batched variants.

The same hook is called on both single and batched variants. For single
transfers, the length of the `id` and `amount` arrays will be 1.

Calling conditions (for each `id` and `amount` pair):

- When `from` and `to` are both non-zero, `amount` of ``from``'s tokens
of token type `id` will be  transferred to `to`.
- When `from` is zero, `amount` tokens of token type `id` will be minted
for `to`.
- when `to` is zero, `amount` of ``from``'s tokens of token type `id`
will be burned.
- `from` and `to` are never both zero.
- `ids` and `amounts` have the same, non-zero length.

To learn more about hooks, head to xref:ROOT:extending-contracts.adoc#using-hooks[Using Hooks]._

### _doSafeTransferAcceptanceCheck

```solidity
function _doSafeTransferAcceptanceCheck(address operator, address from, address to, uint256 id, uint256 amount, bytes data) private
```

### _doSafeBatchTransferAcceptanceCheck

```solidity
function _doSafeBatchTransferAcceptanceCheck(address operator, address from, address to, uint256[] ids, uint256[] amounts, bytes data) private
```

### _asSingletonArray

```solidity
function _asSingletonArray(uint256 element) private pure returns (uint256[])
```

## IERC1155

_Required interface of an ERC1155 compliant contract, as defined in the
https://eips.ethereum.org/EIPS/eip-1155[EIP].

_Available since v3.1.__

### TransferSingle

```solidity
event TransferSingle(address operator, address from, address to, uint256 id, uint256 value)
```

_Emitted when `value` tokens of token type `id` are transferred from `from` to `to` by `operator`._

### TransferBatch

```solidity
event TransferBatch(address operator, address from, address to, uint256[] ids, uint256[] values)
```

_Equivalent to multiple {TransferSingle} events, where `operator`, `from` and `to` are the same for all
transfers._

### ApprovalForAll

```solidity
event ApprovalForAll(address account, address operator, bool approved)
```

_Emitted when `account` grants or revokes permission to `operator` to transfer their tokens, according to
`approved`._

### URI

```solidity
event URI(string value, uint256 id)
```

_Emitted when the URI for token type `id` changes to `value`, if it is a non-programmatic URI.

If an {URI} event was emitted for `id`, the standard
https://eips.ethereum.org/EIPS/eip-1155#metadata-extensions[guarantees] that `value` will equal the value
returned by {IERC1155MetadataURI-uri}._

### balanceOf

```solidity
function balanceOf(address account, uint256 id) external view returns (uint256)
```

_Returns the amount of tokens of token type `id` owned by `account`.

Requirements:

- `account` cannot be the zero address._

### balanceOfBatch

```solidity
function balanceOfBatch(address[] accounts, uint256[] ids) external view returns (uint256[])
```

_xref:ROOT:erc1155.adoc#batch-operations[Batched] version of {balanceOf}.

Requirements:

- `accounts` and `ids` must have the same length._

### setApprovalForAll

```solidity
function setApprovalForAll(address operator, bool approved) external
```

_Grants or revokes permission to `operator` to transfer the caller's tokens, according to `approved`,

Emits an {ApprovalForAll} event.

Requirements:

- `operator` cannot be the caller._

### isApprovedForAll

```solidity
function isApprovedForAll(address account, address operator) external view returns (bool)
```

_Returns true if `operator` is approved to transfer ``account``'s tokens.

See {setApprovalForAll}._

### safeTransferFrom

```solidity
function safeTransferFrom(address from, address to, uint256 id, uint256 amount, bytes data) external
```

_Transfers `amount` tokens of token type `id` from `from` to `to`.

Emits a {TransferSingle} event.

Requirements:

- `to` cannot be the zero address.
- If the caller is not `from`, it must be have been approved to spend ``from``'s tokens via {setApprovalForAll}.
- `from` must have a balance of tokens of type `id` of at least `amount`.
- If `to` refers to a smart contract, it must implement {IERC1155Receiver-onERC1155Received} and return the
acceptance magic value._

### safeBatchTransferFrom

```solidity
function safeBatchTransferFrom(address from, address to, uint256[] ids, uint256[] amounts, bytes data) external
```

_xref:ROOT:erc1155.adoc#batch-operations[Batched] version of {safeTransferFrom}.

Emits a {TransferBatch} event.

Requirements:

- `ids` and `amounts` must have the same length.
- If `to` refers to a smart contract, it must implement {IERC1155Receiver-onERC1155BatchReceived} and return the
acceptance magic value._

## IERC1155Receiver

__Available since v3.1.__

### onERC1155Received

```solidity
function onERC1155Received(address operator, address from, uint256 id, uint256 value, bytes data) external returns (bytes4)
```

_Handles the receipt of a single ERC1155 token type. This function is
called at the end of a `safeTransferFrom` after the balance has been updated.

NOTE: To accept the transfer, this must return
`bytes4(keccak256("onERC1155Received(address,address,uint256,uint256,bytes)"))`
(i.e. 0xf23a6e61, or its own function selector)._

| Name | Type | Description |
| ---- | ---- | ----------- |
| operator | address | The address which initiated the transfer (i.e. msg.sender) |
| from | address | The address which previously owned the token |
| id | uint256 | The ID of the token being transferred |
| value | uint256 | The amount of tokens being transferred |
| data | bytes | Additional data with no specified format |

| Name | Type | Description |
| ---- | ---- | ----------- |
| [0] | bytes4 | `bytes4(keccak256("onERC1155Received(address,address,uint256,uint256,bytes)"))` if transfer is allowed |

### onERC1155BatchReceived

```solidity
function onERC1155BatchReceived(address operator, address from, uint256[] ids, uint256[] values, bytes data) external returns (bytes4)
```

_Handles the receipt of a multiple ERC1155 token types. This function
is called at the end of a `safeBatchTransferFrom` after the balances have
been updated.

NOTE: To accept the transfer(s), this must return
`bytes4(keccak256("onERC1155BatchReceived(address,address,uint256[],uint256[],bytes)"))`
(i.e. 0xbc197c81, or its own function selector)._

| Name | Type | Description |
| ---- | ---- | ----------- |
| operator | address | The address which initiated the batch transfer (i.e. msg.sender) |
| from | address | The address which previously owned the token |
| ids | uint256[] | An array containing ids of each token being transferred (order and length must match values array) |
| values | uint256[] | An array containing amounts of each token being transferred (order and length must match ids array) |
| data | bytes | Additional data with no specified format |

| Name | Type | Description |
| ---- | ---- | ----------- |
| [0] | bytes4 | `bytes4(keccak256("onERC1155BatchReceived(address,address,uint256[],uint256[],bytes)"))` if transfer is allowed |

## IERC1155MetadataURI

_Interface of the optional ERC1155MetadataExtension interface, as defined
in the https://eips.ethereum.org/EIPS/eip-1155#metadata-extensions[EIP].

_Available since v3.1.__

### uri

```solidity
function uri(uint256 id) external view returns (string)
```

_Returns the URI for token type `id`.

If the `\{id\}` substring is present in the URI, it must be replaced by
clients with the actual token type ID._

## Address

_Collection of functions related to the address type_

### isContract

```solidity
function isContract(address account) internal view returns (bool)
```

_Returns true if `account` is a contract.

[IMPORTANT]
====
It is unsafe to assume that an address for which this function returns
false is an externally-owned account (EOA) and not a contract.

Among others, `isContract` will return false for the following
types of addresses:

 - an externally-owned account
 - a contract in construction
 - an address where a contract will be created
 - an address where a contract lived, but was destroyed
====

[IMPORTANT]
====
You shouldn't rely on `isContract` to protect against flash loan attacks!

Preventing calls from contracts is highly discouraged. It breaks composability, breaks support for smart wallets
like Gnosis Safe, and does not provide security since it can be circumvented by calling from a contract
constructor.
====_

### sendValue

```solidity
function sendValue(address payable recipient, uint256 amount) internal
```

_Replacement for Solidity's `transfer`: sends `amount` wei to
`recipient`, forwarding all available gas and reverting on errors.

https://eips.ethereum.org/EIPS/eip-1884[EIP1884] increases the gas cost
of certain opcodes, possibly making contracts go over the 2300 gas limit
imposed by `transfer`, making them unable to receive funds via
`transfer`. {sendValue} removes this limitation.

https://diligence.consensys.net/posts/2019/09/stop-using-soliditys-transfer-now/[Learn more].

IMPORTANT: because control is transferred to `recipient`, care must be
taken to not create reentrancy vulnerabilities. Consider using
{ReentrancyGuard} or the
https://solidity.readthedocs.io/en/v0.5.11/security-considerations.html#use-the-checks-effects-interactions-pattern[checks-effects-interactions pattern]._

### functionCall

```solidity
function functionCall(address target, bytes data) internal returns (bytes)
```

_Performs a Solidity function call using a low level `call`. A
plain `call` is an unsafe replacement for a function call: use this
function instead.

If `target` reverts with a revert reason, it is bubbled up by this
function (like regular Solidity function calls).

Returns the raw returned data. To convert to the expected return value,
use https://solidity.readthedocs.io/en/latest/units-and-global-variables.html?highlight=abi.decode#abi-encoding-and-decoding-functions[`abi.decode`].

Requirements:

- `target` must be a contract.
- calling `target` with `data` must not revert.

_Available since v3.1.__

### functionCall

```solidity
function functionCall(address target, bytes data, string errorMessage) internal returns (bytes)
```

_Same as {xref-Address-functionCall-address-bytes-}[`functionCall`], but with
`errorMessage` as a fallback revert reason when `target` reverts.

_Available since v3.1.__

### functionCallWithValue

```solidity
function functionCallWithValue(address target, bytes data, uint256 value) internal returns (bytes)
```

_Same as {xref-Address-functionCall-address-bytes-}[`functionCall`],
but also transferring `value` wei to `target`.

Requirements:

- the calling contract must have an ETH balance of at least `value`.
- the called Solidity function must be `payable`.

_Available since v3.1.__

### functionCallWithValue

```solidity
function functionCallWithValue(address target, bytes data, uint256 value, string errorMessage) internal returns (bytes)
```

_Same as {xref-Address-functionCallWithValue-address-bytes-uint256-}[`functionCallWithValue`], but
with `errorMessage` as a fallback revert reason when `target` reverts.

_Available since v3.1.__

### functionStaticCall

```solidity
function functionStaticCall(address target, bytes data) internal view returns (bytes)
```

_Same as {xref-Address-functionCall-address-bytes-}[`functionCall`],
but performing a static call.

_Available since v3.3.__

### functionStaticCall

```solidity
function functionStaticCall(address target, bytes data, string errorMessage) internal view returns (bytes)
```

_Same as {xref-Address-functionCall-address-bytes-string-}[`functionCall`],
but performing a static call.

_Available since v3.3.__

### functionDelegateCall

```solidity
function functionDelegateCall(address target, bytes data) internal returns (bytes)
```

_Same as {xref-Address-functionCall-address-bytes-}[`functionCall`],
but performing a delegate call.

_Available since v3.4.__

### functionDelegateCall

```solidity
function functionDelegateCall(address target, bytes data, string errorMessage) internal returns (bytes)
```

_Same as {xref-Address-functionCall-address-bytes-string-}[`functionCall`],
but performing a delegate call.

_Available since v3.4.__

### verifyCallResult

```solidity
function verifyCallResult(bool success, bytes returndata, string errorMessage) internal pure returns (bytes)
```

_Tool to verifies that a low level call was successful, and revert if it wasn't, either by bubbling the
revert reason using the provided one.

_Available since v4.3.__

## Context

_Provides information about the current execution context, including the
sender of the transaction and its data. While these are generally available
via msg.sender and msg.data, they should not be accessed in such a direct
manner, since when dealing with meta-transactions the account sending and
paying for execution may not be the actual sender (as far as an application
is concerned).

This contract is only required for intermediate, library-like contracts._

### _msgSender

```solidity
function _msgSender() internal view virtual returns (address)
```

### _msgData

```solidity
function _msgData() internal view virtual returns (bytes)
```

## ERC165

_Implementation of the {IERC165} interface.

Contracts that want to implement ERC165 should inherit from this contract and override {supportsInterface} to check
for the additional interface id that will be supported. For example:

```solidity
function supportsInterface(bytes4 interfaceId) public view virtual override returns (bool) {
    return interfaceId == type(MyInterface).interfaceId || super.supportsInterface(interfaceId);
}
```

Alternatively, {ERC165Storage} provides an easier to use but more expensive implementation._

### supportsInterface

```solidity
function supportsInterface(bytes4 interfaceId) public view virtual returns (bool)
```

_See {IERC165-supportsInterface}._

## IERC165

_Interface of the ERC165 standard, as defined in the
https://eips.ethereum.org/EIPS/eip-165[EIP].

Implementers can declare support of contract interfaces, which can then be
queried by others ({ERC165Checker}).

For an implementation, see {ERC165}._

### supportsInterface

```solidity
function supportsInterface(bytes4 interfaceId) external view returns (bool)
```

_Returns true if this contract implements the interface defined by
`interfaceId`. See the corresponding
https://eips.ethereum.org/EIPS/eip-165#how-interfaces-are-identified[EIP section]
to learn more about how these ids are created.

This function call must use less than 30 000 gas._

## DispatchAdmin

Controls the Messenger contract

_this contract is the one we interface with on the front-end_

### nft

```solidity
contract Nft nft
```

### tokenIDToTokenOrgAddr

```solidity
mapping(uint256 => address) tokenIDToTokenOrgAddr
```

### walletAddress

```solidity
mapping(address => address) walletAddress
```

### TokenAdded

```solidity
event TokenAdded(address orgAddress, uint256 nftID, address deployerAddress)
```

### TokenRemoved

```solidity
event TokenRemoved(address orgAddress, uint256 nftID, address deployerAddress)
```

### TeamMemberAdded

```solidity
event TeamMemberAdded(address orgAddress, uint256 tokenCounter, address teamMember)
```

### TeamMemberRemoved

```solidity
event TeamMemberRemoved(address orgAddress, address memberAddress)
```

### MessageSent

```solidity
event MessageSent(address orgAddress, uint256 tokenId, string metadata)
```

### constructor

```solidity
constructor(address _MessengerContract) public
```

### onlyAuthorised

```solidity
modifier onlyAuthorised(uint256 _nftID)
```

### verify

```solidity
modifier verify(address _orgAddress, uint256 _nftID)
```

### isUnassignedToWallet

```solidity
modifier isUnassignedToWallet(address _orgAddress)
```

### onlyWallet

```solidity
modifier onlyWallet(address _orgAddress)
```

### setBackendWallet

```solidity
function setBackendWallet(address _orgAddress, address _walletAddress) external
```

Sets the backend wallet for an org. Only owner can set backend wallet for a org.
        @param _orgAddress the token org address 
        @param _walletAddress the wallet address

### addTokenOrg

```solidity
function addTokenOrg(address _orgAddress, address _deployerAddress, address _orgWalletAddress, string _metadata) external
```

Adds a token address to the platform and mints an Admin NFT to the deployer. Only the owner of the contract can add a new token organization.
        @param _orgAddress the token org address 
        @param _deployerAddress the deployer address.
        @param _orgWalletAddress the org wallet address. We mint and send funds to this address.
        @param _metadata metadata for the ADMIN NFT.

### removeTokenOrg

```solidity
function removeTokenOrg(uint256 _nftID, address[] _adminTokensToBurn) external
```

Removes a token from the platform and optionally burns all the Roles NFTs for that particular token. Only the owner of the contract can remove a token.
        @param _nftID the token NFT tokenID
        @param _adminTokensToBurn the address of Admin NFT holders - optional param used to burnAdminNFTs in a single transaction.

### burnAdminNFTs

```solidity
function burnAdminNFTs(address _adminTokenToBurn, uint256 _nftID, address _orgAddress) public
```

Burns all admin NFTs owned by a particular address. The owner OR the admin can call this function.
        @param _adminTokenToBurn the address of Admin NFT holders - optional param used to burnAdminNFTs in a single transaction.
        @param _nftID the token NFT tokenID
        @param _orgAddress the address of the token org

### burnMessageNFTs

```solidity
function burnMessageNFTs(address[] _messageTokenToBurn, uint256 _nftID) external
```

Burns all message NFTs owned by a particular address. the superadmin can call this function.
        @param _messageTokenToBurn the address of message NFT holders - optional param used to burnAdminNFTs in a single transaction.
        @param _nftID the token NFT tokenID

### addTeamMember

```solidity
function addTeamMember(uint256 _nftID, address _orgAddress, address _teamMember) external
```

Adds a team member address to a token and mints NFT to the team member. Only Owner or the admin of the token can add a team member.
        @param _nftID the nft ID of the msg.sender(ADMIN)
        @param _orgAddress the token org address 
        @param _teamMember the team member address.

### removeTeamMember

```solidity
function removeTeamMember(uint256 _nftID, address _orgAddress, address _adminTokenToBurn) external
```

Removes a team member address from a token and burns the NFT from the team member. Only Owner or the admin of the token can remove a team member.
        @param _nftID the nft ID of the msg.sender(ADMIN)
        @param _orgAddress the token org address 
        @param _adminTokenToBurn the team member address.

### mintMessage

```solidity
function mintMessage(uint256 _nftID, address _orgAddress, uint256 _amount, string _metadata) external payable
```

Mints the message NFT to the backend wallet. Only org Admin can mint the NFTs.
        @param _nftID the nft ID of the msg.sender(ADMIN)
        @param _orgAddress the token org address 
        @param _metadata the metadata for Message NFT 
        @param _amount the amount of messages to mint

### sendNFTs

```solidity
function sendNFTs(address _orgAddress, address[] _to, uint256 _messageID) external
```

Sends Message as an NFT to the filtered token holders. Only backend wallet can send the NFTs to the holders.
        @param _orgAddress the token org address 
        @param _to list of filtered token holder address
        @param _messageID the ID of the message NFT

## DispatchMessenger

after deploying the contract, transfer the ownership to DispatchAdmin contract.

_this contract is entirely controlled by the Admin contract_

### constructor

```solidity
constructor() public
```

### mint

```solidity
function mint(address _to, uint256 _amount, string _metadata) external returns (uint256)
```

Mints tokens to an address. Meant to be tokenOrg's wallet address
        @param _to where we send the NFT. Meant to be the org wallet address
        @param _amount of tokens to mint
        @param _metadata metadata for the MESSAGE NFT

### burnMessage

```solidity
function burnMessage(address _from, uint256 _id, uint256 _amount) external
```

Burns tokens at an address. Allows for owner to burn messages
        @param _from where we send the NFT. Meant to be the org wallet address
        @param _id of token to burn
        @param _amount quantity to burn

### isApprovedForAll

```solidity
function isApprovedForAll(address _owner, address _operator) public view returns (bool isOperator)
```

Override isApprovedForAll to auto-approve OS's proxy contract

| Name | Type | Description |
| ---- | ---- | ----------- |
| _owner | address | of the token |
| _operator | address | to be approved |

## NFTMetadata

this is an abstract contract and is meant to be extended

_remember that Admin and Messenger use their own instance of this same base contract_

### tokenCounter

```solidity
uint256 tokenCounter
```

### name

```solidity
string name
```

### symbol

```solidity
string symbol
```

### tokenURI

```solidity
mapping(uint256 => string) tokenURI
```

### _setTokenURI

```solidity
function _setTokenURI(uint256 _tokenCounter, string _metadata) internal
```

Sets the URI metadata for a particular nftID
        @param _tokenCounter the nftID
        @param _metadata metadata for the MESSAGE NFT

### uri

```solidity
function uri(uint256 _id) public view returns (string)
```

Returns the metadata URI of an nftID
        @param _id the nftID

## Nft

### balanceOf

```solidity
function balanceOf(address account, uint256 id) external returns (uint256)
```

### mint

```solidity
function mint(address _to, uint256 amount, string _metadata) external returns (uint256)
```

### safeTransferFrom

```solidity
function safeTransferFrom(address from, address to, uint256 id, uint256 amount, bytes data) external
```

### burnMessage

```solidity
function burnMessage(address from, uint256 id, uint256 amount) external
```

