# Задача: посчитать количество блоков в графе

## Определение
Пусть G — связный граф. Вершина a ∈ V (G) называется точкой сочленения, если граф G − a несвязен.
Блоком называется любой максимальный по включению подграф графа G, не имеющий точек сочленения
1) Блок графа G либо является двусвязным графом, либо блок связен и содержит не более двух вершин.
2) В силу максимальности, блок графа G является индуцированным подграфом графа G на своем множестве вершин.
3) Любой подграф без точек сочленения H графа G входит хотя бы в один блок (так как H можно дополнить до максимального подграфа
без точек сочленения).

## Реализация алгоритма

Проверим, выполняются ли данные свойства для реализованного алгоритма:

1) Блок графа G либо является двусвязным графом, либо блок связен и содержит не более двух вершин.

    Алгоритм реализует метод для подсчета двусвязных компонент (блоков) в графе. Он использует метод поиска в глубину (DFS) для нахождения всех точек сочленения и ребер, которые отделяют двусвязные компоненты. Блоки определяются как максимальные подграфы, которые остаются связными после удаления любой вершины. Это согласуется с утверждением, что блок графа либо является двусвязным графом, либо блок связен и содержит не более двух вершин. Алгоритм корректно выявляет эти компоненты, так как он проверяет условия для вершин и ребер, чтобы разделить граф на блоки.

2) В силу максимальности, блок графа G является индуцированным подграфом графа G на своем множестве вершин.

    Алгоритм создает блоки путем последовательного добавления ребер в стек и последующего формирования блоков при выявлении точек сочленения. Поскольку блоки формируются из исходных вершин и ребер графа, и каждое ребро добавляется в стек только один раз, каждый блок является индуцированным подграфом исходного графа, что подтверждает это свойство.

3) Любой подграф без точек сочленения H графа G входит хотя бы в один блок (так как H можно дополнить до максимального подграфа без точек сочленения).

    Алгоритм выявляет все блоки путем поиска двусвязных компонент. Любой подграф без точек сочленения будет целиком находиться внутри одного из таких блоков, так как он не может быть разделен на части удалением одной вершины. Это также означает, что любой такой подграф будет максимальным по включению подграфом без точек сочленения.