# Binary-Tree-Level-Order-Traversal

vector<vector<int>> levelOrder(TreeNode* root) {
        vector<vector<int>> ans;
        queue<TreeNode*> q;
        q.push(root);

        if(root==0)
            return ans;

        while(!q.empty()){
            int size=q.size();
            vector<int> subans;
            
            for(int i=0; i<size; i++){
                TreeNode* top = q.front();
                q.pop();

                subans.push_back(top->val);

                if(top->left)
                    q.push(top->left);
                if(top->right){
                    q.push(top->right);
                }
            }
            ans.push_back(subans);
        }

        return ans;
    }
