# permutations: Este código genera todas las permutaciones posibles de los elementos en la lista proporcionada mediante una función recursiva.
def permutations(list : List[String]): List[String] = {

  def helper(head: String, tail: List[String]): List[String] = {
    if (tail.isEmpty) {
      List(head)
    } else {
      tail.flatMap { elem =>
        val newHead = head + elem
        val newTail = tail.filterNot(_ == elem)
        helper(newHead, newTail)
      }
    }
  }
  helper("",list)
}


println(permutations(List("a","b","c")))
