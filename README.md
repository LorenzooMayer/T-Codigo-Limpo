public class Lista {
    private Nodo inicio;

    public Lista() {
        this.inicio = null;
    }

    public void insereLista(int valor) {
        Nodo novo = new Nodo();
        novo.setValor(valor);
        novo.setProximo(null);

        if (inicio == null) {
            inicio = novo;
        } else {
            Nodo aux = inicio;
            while (aux.getProximo() != null) {
                aux = aux.getProximo();
            }
            aux.setProximo(novo);
        }
    }

    public void imprimeLista() {
        Nodo aux = inicio;
        int cont = 0;
        while (aux != null) {
            System.out.println(aux.getValor());
            cont++;
            aux = aux.getProximo();
        }
        System.out.println("Total de nodos: " + cont);
    }

    public void removeIL() {
        if (inicio == null) {
            System.out.println("Lista vazia!");
        } else {
            inicio = inicio.getProximo();
        }
    }

    public void pesquisaLista(int valor) {
        int pos = 1;
        Nodo aux = inicio;
        while (aux != null && aux.getValor() != valor) {
            pos++;
            aux = aux.getProximo();
        }
        if (aux != null) {
            System.out.println("Valor " + valor + " encontrado na posição: " + pos);
        } else {
            System.out.println("Valor " + valor + " não encontrado!");
        }
    }

    public void insereIL(int valor) {
        Nodo novo = new Nodo();
        novo.setValor(valor);
        novo.setProximo(inicio);

        inicio = novo;
    }

    public void removeFL() {
        if (inicio == null) {
            System.out.println("Lista vazia!");
        } else if (inicio.getProximo() == null) {
            inicio = null;
        } else {
            Nodo aux = inicio;
            while (aux.getProximo().getProximo() != null) {
                aux = aux.getProximo();
            }
            aux.setProximo(null);
        }
    }
}
