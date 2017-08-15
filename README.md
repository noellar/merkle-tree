# merkle-tree

This library implements a merkle-tree data structure, for representing a list of
hashed data as a binary tree of pairs of hashes converging to a single hash, the
`merkle root`. SHA3_256 is used as the hashing algorithm.

# Example

```haskell
import Crypto.Hash.MerkleTree

example :: Bool
example = 
    -- Does the proof prove that `mleaf` exists in `mtree`? 
    validateMerkleProof proof (mtRoot mtree) mleaf 
  where
    -- Build a merkle tree from a list of data
    mtree = mkMerkleTree ["tx1", "tx2", "tx3"] 
    mleaf = mkLeafRootHash "tx2"
    -- Construct merkle proof that a leaf exists in `merkleTree`
    proof = merkleProof mtree mleaf
```

# TODO
- Explain merkle tree construction
- Explain merkle proofs and what they are used for
