labels: bug

body:
- type: markdown
  attributes:
    value: >
      #### Before submitting a bug, please make sure the issue hasn't been already addressed by searching through [the existing and past issues](https://github.com/pyg-team/pytorch_geometric/issues).
      #
- type: textarea
  attributes:
    label: 🐛 Describe the bug
    description: |
      Please provide a clear and concise description of the bug.
      If relevant, add a minimal example so that we can reproduce the error by running the code. It is very important for the snippet to be as minimal as possible, so please take time to trim down any irrelevant code to help us debug efficiently. We are going to copy-paste your code and we expect to get the same result as you did: avoid any external data, and include the relevant imports:
      ```python
      # All necessary imports at the beginning
      import torch
      from torch_geometric.utils import to_undirected
      # A minimal reproducing example trimmed down to the essential parts:
      edge_index = torch.tensor([[0, 1, 2], [1, 2, 3]])
      edge_index = to_undirected(edge_index, num_nodes=1)
      assert edge_index.size(1) == 6  # We expect that the number of edges is doubled.
      # NOTE: the bug is that num_nodes < edge_index.max() + 1
      ```
      Please also paste or describe the results you observe instead of the expected results. If you observe an error, please paste the error message including the **full** traceback of the exception. It may be relevant to wrap error messages in ```` ```triple quotes blocks``` ````.
    placeholder: |
      A clear and concise description of the bug.
      ```python
      # Sample code to reproduce the problem
      ```
      ```
      The error message you got, with the full traceback.
      ```
  validations:
    required: true
- type: textarea
  attributes:
    label: Environment
    description: |
      Please provide as much information as possible about your environment, such as your PyG (`print(torch_geometric.__version__)`) and PyTorch version (`print(torch.__version__)`), your OS (*e.g.*, Linux), and your Python version (*e.g.*, `3.9`):
    value: |
      * PyG version:
      * PyTorch version:
      * OS:
      * Python version:
      * CUDA/cuDNN version:
      * How you installed PyTorch and PyG (`conda`, `pip`, source):
      * Any other relevant information (*e.g.*, version of `torch-scatter`):
