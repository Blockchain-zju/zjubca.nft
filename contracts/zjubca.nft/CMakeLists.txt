cmake_minimum_required(VERSION 3.5)
project(zjubca.nft VERSION 1.0.0)

find_package(eosio.cdt)

# add contract
add_contract( zjubca.nft zjubca.nft zjubca.nft.cpp )
