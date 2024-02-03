import hashlib
import time
import random

class Block:
    def __init__(self, index, previous_hash, timestamp, data, hash, validator):
        self.index = index
        self.previous_hash = previous_hash
        self.timestamp = timestamp
        self.data = data
        self.hash = hash
        self.validator = validator

def calculate_hash(index, previous_hash, timestamp, data, validator):
    value = str(index) + str(previous_hash) + str(timestamp) + str(data) + str(validator)
    return hashlib.sha256(value.encode('utf-8')).hexdigest()

def stake_validator():
    validators = ["Validator1", "Validator2", "Validator3"]  # Replace with actual validator addresses
    return random.choice(validators)

def create_genesis_block():
    return mine_block(0, "0", int(time.time()), "Genesis Block")

def mine_block(index, previous_hash, timestamp, data):
    validator = stake_validator()
    hash_value = calculate_hash(index, previous_hash, timestamp, data, validator)
    return Block(index, previous_hash, timestamp, data, hash_value, validator)

def create_new_block(previous_block, data):
    index = previous_block.index +
    
    timestamp = int(time.time())
    return mine_block(index, previous_block.hash, timestamp, data)

# Example usage:
blockchain = [create_genesis_block()]
previous_block = blockchain[0]

# Add blocks to the blockchain
num_blocks_to_add = 5
for _ in range(num_blocks_to_add):
    new_data = f"Block #{previous_block.index + 1}"
    new_block = create_new_block(previous_block, new_data)
    blockchain.append(new_block)
    previous_block = new_block

# Print the blockchain
for block in blockchain:
    print(f"Index: {block.index}")
    print(f"Previous Hash: {block.previous_hash}")
    print(f"Timestamp: {block.timestamp}")
    print(f"Data: {block.data}")
    print(f"Hash: {block.hash}")
    print(f"Validator: {block.validator}")
    print("\n")
