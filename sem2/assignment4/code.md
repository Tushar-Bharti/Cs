# MainCode
```c
#include <stdio.h>
#include <stdlib.h>
#include <limits.h>
#include <string.h>

#define EMPTY_TREE "TREE IS EMPTY"
#define ELEMENT_404 "ELEMENT NOT FOUND IN TREE"
#define true 1
#define false 0

struct Node
{
    int data;
    struct Node *left;
    struct Node *right;
};

struct BinaryTree
{
    struct Node *root;
    int size;
};

struct BinaryTree *createTree()
{
    struct BinaryTree *tree = (struct BinaryTree *)malloc(sizeof(struct BinaryTree));
    tree->root = NULL;
    tree->size = 0;
    return tree;
}
//q1
void _insert(struct Node *data, struct Node *node, struct Node *parent)
{
    if (node == NULL)
    {
        node = data;
        node->left = NULL;
        node->right = NULL;
        if (parent != NULL)
        {
            if (data->data <= parent->data)
            {
                parent->left = node;
            }
            else
            {
                parent->right = node;
            }
        }
        return;
    }
    if (data->data <= node->data)
    {
        return _insert(data, node->left, node);
    }
    else
    {
        return _insert(data, node->right, node);
    }
}
//q1
void add(int item, struct BinaryTree *tree)
{
    struct Node *node = (struct Node *)malloc(sizeof(struct Node));
    node->data = item;
    node->left = NULL;
    node->right = NULL;
    if (tree->root == NULL)
    {
        tree->root = node;
        tree->root->left = NULL;
        tree->root->right = NULL;
        tree->size++;
        return;
    }
    else
    {
        _insert(node, tree->root, NULL);
        tree->size++;
    }
}
//q1
struct Node *findMin(struct Node *node)
{
    struct Node *tempData = (struct Node *)malloc(sizeof(struct Node));
    tempData->data = INT_MAX;
    struct Node *temp = node;
    while (temp != NULL)
    {
        if (temp->data < tempData->data)
        {
            tempData = temp;
            break;
        }
        temp = temp->right;
    }
    return tempData;
}
// q1
struct Node *_delete(struct Node *node, int data)
{
    struct Node *temp;

    if (node == NULL)
    {
        printf(ELEMENT_404);
        return NULL;
    }
    else if (data < node->data)
    {
        node->left = _delete(node->left, data);
    }
    else if (data > node->data)
    {
        node->right = _delete(node->right, data);
    }
    else
    {
        if (node->right && node->left)
        {
            temp = findMin(node->right);
            node->data = temp->data;
            node->right = _delete(node->right, temp->data);
        }
        else
        {
            temp = node;

            if (node->left == NULL)
                node = node->right;
            else if (node->right == NULL)
                node = node->left;

            free(temp);
        }
    }

    return node;
}
// q1
struct Node *delete (int item, struct BinaryTree *tree)
{
    if (tree->root == NULL)
    {
        printf(EMPTY_TREE);
        return NULL;
    }
    tree->size--;
    return _delete(tree->root, item);
}
// q1
struct Node *_search(int item, struct Node *node)
{
    if (node == NULL)
    {
        printf(ELEMENT_404);
        return NULL;
    }
    if (item < node->data)
    {
        _search(item, node->left);
    }
    else if (item > node->data)
    {
        _search(item, node->right);
    }
    else
    {
        return node;
    }
}
// q1
struct Node *search(int item, struct BinaryTree *tree)
{
    if (tree->root == NULL)
    {
        printf(EMPTY_TREE);
        return NULL;
    }

    return _search(item, tree->root);
}
// q2
void _inOrder(struct Node *node)
{
    if (node == NULL)
    {
        return;
    }
    _inOrder(node->left);
    printf("\n|-----------------------------------------------------|\n");
    printf("  Data -> %d [ Address -> %p ]  ", node->data, node);
    printf("\n|-----------------------------------------------------|\n");
    printf("                                                       =>");
    _inOrder(node->right);
}
// q2
void _preOrder(struct Node *node)
{
    if (node == NULL)
    {
        return;
    }
    printf("\n|-----------------------------------------------------|\n");
    printf("  Data -> %d [ Address -> %p ]  ", node->data, node);
    printf("\n|-----------------------------------------------------|\n");
    printf("                                                       =>");
    _preOrder(node->left);
    _preOrder(node->right);
}
// q2
void _postOrder(struct Node *node)
{
    if (node == NULL)
    {
        return;
    }
    _postOrder(node->left);
    _postOrder(node->right);
    printf("\n|-----------------------------------------------------|\n");
    printf("  Data -> %d [ Address -> %p ]  ", node->data, node);
    printf("\n|-----------------------------------------------------|\n");
    printf("                                                       =>");
}
// q2
void printInorder(struct BinaryTree *tree)
{
    if (tree->root == NULL)
    {
        printf(EMPTY_TREE);
        return;
    }
    _inOrder(tree->root);
    printf("  NULL /");
    return;
}
// q2
void printPreorder(struct BinaryTree *tree)
{
    if (tree->root == NULL)
    {
        printf(EMPTY_TREE);
        return;
    }
    _preOrder(tree->root);
    printf("  NULL /");
    return;
}
// q2
void printPostorder(struct BinaryTree *tree)
{
    if (tree->root == NULL)
    {
        printf(EMPTY_TREE);
        return;
    }
    _postOrder(tree->root);
    printf("  NULL /");
    return;
}
// q3
int _fetchSize(struct Node *node)
{
    if (node == NULL)
        return 0;
    else
        return (_fetchSize(node->left) + 1 + _fetchSize(node->right));
}
// q3
int fetchSize(struct BinaryTree *tree)
{
    if (tree->root == NULL)
        return 0;

    return _fetchSize(tree->root);
}

int main(void)
{
    printf("Creating BST\n");
    struct BinaryTree *tree = createTree();
    printf("BST created (Address -> %p)\n", tree);

    char input[100];
    printf("available methods->\n add <item> , delete <item> , search <item> , inorder , preorder , postorder , size , fetchsize , exit\n->");

    while (true)
    {
        scanf("%s", input);
        if (strcmp(input, "add") == 0)
        {
            int item;
            scanf("%d", &item);

            add(item, tree);
            printf("ADDED %d\n->", item);
        }
        else if (strcmp(input, "delete") == 0)
        {
            int item;
            scanf("%d", &item);

            delete (item, tree);
            printf("DELETED %d\n->", item);
        }
        else if (strcmp(input, "search") == 0)
        {
            int item;
            scanf("%d", &item);

            struct Node *res = search(item, tree);
            printf("\nSEARCH RESULT ADDRESS: %p\n->", res);
        }
        else if (strcmp(input, "inorder") == 0)
        {
            printf("\n\nINORDER TRAVERSAL PRINT\n");
            printInorder(tree);
            printf("\n->");
        }
        else if (strcmp(input, "preorder") == 0)
        {
            printf("\n\nPREORDER TRAVERSAL PRINT\n");
            printPreorder(tree);
            printf("\n->");
        }
        else if (strcmp(input, "postorder") == 0)
        {
            printf("\n\nPOSTORDER TRAVERSAL PRINT\n");
            printPostorder(tree);
            printf("\n->");
        }
        else if (strcmp(input, "exit") == 0)
        {
            printf("exit\n");
            break;
        }
        else if (strcmp(input, "size") == 0)
        {
            // q3
            printf("TREE SIZE: %d\n->", tree->size);
        }
        else if (strcmp(input, "fetchsize") == 0)
        {
            // q3
            printf("FETCHED TREE SIZE: %d\n->", fetchSize(tree));
        }
        else
        {
            printf("invalid command\n->");
        }
    }

    return 0;
}
```
