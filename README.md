#ifndef INDEXER_H
#define INDEXER_H

#define WORD_SIZE 100
#define TABLE_SIZE 1009

typedef struct DocNode {
    int docID;
    int freq;
    struct DocNode *next;
} DocNode;

typedef struct HashNode {
    char word[WORD_SIZE];
    DocNode *docs;
    struct HashNode *next;
} HashNode;

extern HashNode *hashTable[TABLE_SIZE];

void build_index(const char *directory);
void insert_word(const char *word, int docID);
void search_word(const char *word);
void to_lowercase(char *s);

#endif
