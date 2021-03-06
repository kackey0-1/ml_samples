# [Understanding Software Architecture Spec] Pipeline Architecture

## Pipeline Architecture Topology
The basic principle behind Unix terminal shell languages such as Bash and Zsh is familiarity with this architecture.
And Pipeline Architecture is used in functional programing languages like MapReduce Programing model.

<div class="mxgraph" style="max-width:100%;border:1px solid transparent;" data-mxgraph="{&quot;highlight&quot;:&quot;#0000ff&quot;,&quot;nav&quot;:true,&quot;resize&quot;:true,&quot;toolbar&quot;:&quot;zoom layers tags lightbox&quot;,&quot;edit&quot;:&quot;_blank&quot;,&quot;xml&quot;:&quot;&lt;mxfile host=\&quot;app.diagrams.net\&quot; modified=\&quot;2022-05-31T07:58:22.217Z\&quot; agent=\&quot;5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/102.0.5005.61 Safari/537.36\&quot; etag=\&quot;XS8MPJg0hH79_rMIax47\&quot; version=\&quot;18.1.1\&quot; type=\&quot;google\&quot;&gt;&lt;diagram id=\&quot;m9_Bpx2jhqHkKHG2KxBJ\&quot; name=\&quot;Page-1\&quot;&gt;7VjLcpswFP0alsmAAD+WjWM7nT6mjTNpslRBBiUCUVkY6NdXGGHAsjPOmBrq6Qru0dXrnCMhoZmTIJ0zGPlfqIuIBnQ31cxbDQDDAgPxyJGsQIaDcQF4DLsyqQIW+DeSoC7RGLto1UjklBKOoybo0DBEDm9gkDGaNNOWlDR7jaCHFGDhQKKiP7DL/QIdgWGF3yHs+WXPRjm/AJbJciYrH7o0qUHmVDMnjFJevAXpBJGcvJKXot7sQOl2YAyF/JgKL3fzzP6aOaPkE7z/GMNZSAZXhj4q2llDEsspy+HyrOSA0Th0Ud6MoZk3iY85WkTQyUsTobrAfB4QWawOS450jRhHaQ2Sw5wjGiDOMpFSlup2UUV6xpBhUglgjyWrfo18AUvhpejetumKF/EiqXkXTWOFphu4wo6AHmhECfUyhTYxW97kZsUZfUUTkc4EEtJQZN4sMSE7ECTYC0VI0DJvIWcOC0t+kHCAXTfvZK8UlVh6S2oAq6EGsHRFDrBPDlM/XY3xoxd8JwaDPx/IKyeTe4v/urIVqpErFq0MKeM+9WgIybRCd2ipcj5TGkl1XhDnmdyBYMxpUzuUYv5Ue3/Om7q2ZXSbypY3QVYGoZjuUz2o1crDqtomyhqq5ZM6uNYltKIxc9AbXJV7JmQe4m/kgf0eYIhAjtfNcbQuaOnJanHNMOGItbETKUbfw+Nh7w/0hveHqvUNcE7rD/5b/2jrgyOtb3ZpfdBX65tWz6w/7NL6ld2fayX7rd+ihc0jLWx1aWGzrxa2Qc8sXF5qOvLwO7bvFj1sHenhcZcetv4VD29PJJ2ZWL0J9YSq3S9W91QZ6sH2G46QwtTpN0VHcCQkaOGueJIE23uglMBWFbDOKoB6vLpsAaxhzwRQDweXLYC9swIMA1yrv6/Oq4H6cbtsDXYXgWH9RQ1EWP3D3ZTV/oSb0z8=&lt;/diagram&gt;&lt;/mxfile&gt;&quot;}"></div>
<script type="text/javascript" src="https://viewer.diagrams.net/js/viewer-static.min.js"></script>

## Specification

### Pipe
- Pipes form a one-way communication between filters, which is typically P2P connection.
- In this architecture, pipes are generally unidirectional (not broadcast) for reasons of communication channel ministrations between filters.
 
### Filter
Filters are self-contained and independent of other filters.
And filter performs only one task.

- Producer Filter
  - Starting point of the process.
- Transformer Filter
  - Receives input, optionally transforms some or all of the data, takes it, and sends it to the output pipe. 
- Tester Filter
  - Receives input, examines it for one or more criteria, and optionally generates output based on the examination
- Consumer Filter
  - The end point of the pipeline flow. 
  - The consumer persists the end result of the pipeline process in a database or displays it in the user interface.

## Example Usage with Kafka

<div class="mxgraph" style="max-width:100%;border:1px solid transparent;" data-mxgraph="{&quot;highlight&quot;:&quot;#0000ff&quot;,&quot;nav&quot;:true,&quot;resize&quot;:true,&quot;toolbar&quot;:&quot;zoom layers tags lightbox&quot;,&quot;edit&quot;:&quot;_blank&quot;,&quot;xml&quot;:&quot;&lt;mxfile host=\&quot;app.diagrams.net\&quot; modified=\&quot;2022-05-31T08:06:19.545Z\&quot; agent=\&quot;5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/102.0.5005.61 Safari/537.36\&quot; etag=\&quot;B8ZTOWkc9U-c82l5OHnu\&quot; version=\&quot;18.1.1\&quot; type=\&quot;google\&quot;&gt;&lt;diagram id=\&quot;m9_Bpx2jhqHkKHG2KxBJ\&quot; name=\&quot;Page-1\&quot;&gt;3Vpbc9o4FP41zLQPyfiCbXgMJqSZdjtsk902Txlhy7Ya2fLKMpf++kpYviFDyUACbCYJ1qeLj86n7+jIpme68fKOgjT6i/gQ9wzNX/bMcc8w9L5h8w+BrArEsYcFEFLky0Y18IB+QQlqEs2RD7NWQ0YIZihtgx5JEuixFgYoJYt2s4Dg9l1TEEIFePAAVtHvyGdRgQ4Mp8Y/QRRG5Z31cn4xKBvLmWQR8MmiAZm3PdOlhLDiKl66EAvnlX4p+k221FaGUZiwfTr8/HS3sr6uvMHiM/h2n4NJgu0rXRsU48wBzuWUpblsVfqAkjzxoRhG75mjRYQYfEiBJ2oXnHWORSzGslo1S1o6h5TBZQOSZt5BEkNGV7xJWatZRRe5ZnRZXNQEWEPp1ajhfLPsByTpYTV07Rd+IV3zKjcNFTfdLkGcchcZGgn4vylKIUaJKN9QT/jIYzmFijO5D1jbYxmj5AW6BBPKkYTwMcxRgDDegABGYcKLGAZiBOFPxBfqjYRj5PviJp0E1RRqR+KoFKjkyCyXeYMko5ukwznqL2D6K9cNyIx0Mqfk+9dwdqXbiq+hz7Usi4SyiIQkAfi2Rjf8Urf5Qkgq6fkJGVvJwARyRtrkwSViPxrXT2Koa0uWxks58rqwKgsJn++PZqHRSxTrbuvSqkWbmNTWECChjOTUk62G/4bx31inYPaIXxh2v/XZf1dlKAU0hGyHU63uRUAhBgzN23YcwuguIxuae4B0jjyhsfskIPzDBWmhMhsLTcwovwrF1YcKKpEpJX7uQVpWcJOquo8nj3mG3dZTX415leSacuq/lZz6F6MmXphCivi0IT1IKd1hRVXK9sX6DkrZZeSuTTx7gcyLpH9SghK2NsIa8V++htziz+JNXYFcG1YH2IU5KqirzfiH3nWHTbALc1RQV5uJUml1G+zCHEu1eLO33tFb3+jNf/lKz5nY+t0qBxU+DkjCyh28x/dH05gIRkchBT6Crbph3xpPjEbdGFE+ECLJevenIgK0MgLex7oxtZGlpA+8Jlj/8BofZFGlxjJd+AJmEE9JhuTwM8IYiTvyCSY0WyUdHrdKyKupVjFDKWXdKMtyxYlbgiwt3BGgpbBjxFPgVFTGy1CcFq7BIutfU1ho8N4T9ox4sbhqt4pBwlNt/5nPFoIYJeFzQOjzCwheQKV3Jdp2KH57QrMZgNV8xuqIv9ZbxV9DkfTn9WSPn09W1B6cUR5GgNUmYKgS4LxnPmnuEVPXni7PhcYGDRuLPcBk4UWAsmsfMDAD2TbPHsGXltb2ZeW5hjPt98wmdOdi0ol3Tc63J917JOf2KVOO6rHGSRitWXxq1PyJ0ZrEpxaHZ8Ooc0pGLSXgjXMK1mmCoU0QZvXZqT5nKcesD13nK6XVI8xY91FMafqxu9Xh57WDImxfO7Pzmj64lAh7RF0dGgFl16k4DtXc2k6bW3vjsWIhY9lpg7bKigMiq35KJl8TWY/N5B4RcnDKCGkrEfKflKEYvio+FqHvPKOa1T+3qHbSx1AXlmU4e2poeEoNObuyDBdgL+dWkA4lqU90HylIsoDQ+A0f6h41SdA7XpK8s57UQ+yZ6umIuhhcgi7U97DV3tKhisb2AmKxcJNZlja3m1o2DZVcxqZzBir5359t16U3fGsy3FNy5iklp77T/2M6p25CLkmy/Hx3IKf9VQpDeztt8WL9bZbiMFR/J8i8/Q0=&lt;/diagram&gt;&lt;/mxfile&gt;&quot;}"></div>
<script type="text/javascript" src="https://viewer.diagrams.net/js/viewer-static.min.js"></script>

## Architecture Evaluation
| Architecture Spec | Score |
|-------------------|-------|
| Separate Type     | Tech  |
| Quantum Number    | 1     |
| Deployment Ease   | 2     |
| Elasticity        | 1     |
| Evolvability      | 3     |
| Resiliency        | 1     |
| Modularity        | 3     |
| Overall Cost      | 5     |
| Performance       | 2     |
| Reliability       | 3     |
| Scalability       | 1     |
| Simplicity        | 5     |
| Testability       | 3     |

