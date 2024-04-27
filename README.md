public class Lista {
	private Nodo inicio;

	public Lista() {
		this.inicio = null;
	}
	
	public void insereLista(int valor) {
		Nodo novo = new Nodo();
		novo.setValor(valor);
		novo.setProximo(null);
		
		if(this.inicio == null)
			this.inicio = novo;
		else {
			Nodo aux = this.inicio;
			while(aux.getProximo() != null) {
				aux = aux.getProximo();
			}
			aux.setProximo(novo);
		}
	}
	
	public void imprimeLista() {
		Nodo aux = this.inicio;
		int cont = 0;
		while(aux != null) {
			System.out.println(aux.getValor());
			cont++;
			aux = aux.getProximo();
		}
		System.out.println("Total de nodos: "+cont);
		
	}
	
	public void removeInicioLista() {
		if(this.inicio == null)
			System.out.println("Lista vazia!");
		else {
			Nodo aux =  this.inicio;
			this.inicio = this.inicio.getProximo();
			aux = null;
		}
	}
	
	public void pesquisaLista(int valor) {
		int pos = 1;
		if(this.inicio == null)
			System.out.println("Lista vazia!");
		else {
			Nodo aux = this.inicio;
			while(aux != null && aux.getValor() != valor) {
				pos++;
				aux = aux.getProximo();
			}
			if(aux != null)
				System.out.println("Valor "+valor+" encontrado na posi��o: "+pos); 
			else
				System.out.println("Valor "+valor+" n�o encontrado!");
		}
	}
	
	public void insereInicioLista(int valor) {
		Nodo novo = new Nodo();
		novo.setValor(valor);
		novo.setProximo(this.inicio);
		
		this.inicio = novo;
	}
	
	public void removeFinalLista() {
		if(this.inicio == null)
			System.out.println("Lista vazia!");
		else {
			if(this.inicio.getProximo() == null) {
				this.inicio = null;
			}
			else {
				Nodo aux = this.inicio;
				while(aux.getProximo().getProximo() != null) {
					aux = aux.getProximo();
				}
				aux.setProximo(null);
			}
		}
	}
	
	
}
