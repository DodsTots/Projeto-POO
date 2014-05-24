package projeto.poo;

import javax.swing.JOptionPane;

public class ProjetoPOO
{
    public static void main( String[] args )
    {
        
        String s = null;
        int decisao;
        int menu = 0;
        
        //LOOP GLOBAL, AO SAIR DELE O JOGO ACABA E FECHA
        while ( true )
        {
            
            //LOOP O MENU INICIAL DO JOGO
            while ( true )
            {
                try
                {
                    s = JOptionPane.showInputDialog( "0 - Novo jogo\n1 - Carregar\n2 - Sair" );
                    decisao = Integer.parseInt( s );
                }
                catch ( NumberFormatException e )
                {
                    JOptionPane.showMessageDialog( null, "Tente novamente" );
                    continue;
                }
                break;
            }
            
            //CASO O JOGO SEJA INICIADO
            if ( decisao == 0 )
            {
                
                //INICIALIZAÇÃO DE UMA HISTÓRIA NOVA E UM PERSONAGEM NOVO
                HistoriaPrincipal historiaPrincipal = new HistoriaPrincipal();
                Personagem personagem = new Personagem();
                
                //LOOP PARA CRIAÇÃO DO PERSONAGEM
                while ( true )
                {
                    
                    //DEFINIÇÃO DO NOME
                    if ( menu == 0 )
                    {
                        personagem.setNome(JOptionPane.showInputDialog(historiaPrincipal.getHistoriaPrincipal(personagem.getPartHistoria())));
                        personagem.aumentaPartHistoria();
                        menu = menu + 1;
                    }
                    
                    //DEFINIÇÃO DO SEXO
                    if ( menu == 1 )
                    {
                        while ( true )
                        {
                            personagem.setSexo(JOptionPane.showConfirmDialog(null, historiaPrincipal.getHistoriaPrincipal(personagem.getPartHistoria())));
                            personagem.aumentaPartHistoria();
                            menu++;
                            if ( personagem.getSexo() == 2 )
                            {
                                personagem.diminuiPartHistoria();
                                personagem.diminuiPartHistoria();
                                menu = menu - 2;
                                break;
                            }
                            break;
                        }
                    }
                    
                    //DEFINIÇÃO DA VANTAGEM
                    if ( menu == 2 )
                    {
                        while ( true )
                        {
                            try
                            {
                                s = JOptionPane.showInputDialog(historiaPrincipal.getHistoriaPrincipal(personagem.getPartHistoria()));
                                decisao = Integer.parseInt( s );
                                personagem.setVantagem(decisao);
                            }
                            catch ( NumberFormatException e )
                            {
                                JOptionPane.showMessageDialog( null, "Tente novamente" );
                                continue;
                            }
                            
                            if ( decisao == 0 )
                            {
                                personagem.diminuiPartHistoria();
                                personagem.diminuiPartHistoria();
                                menu = menu - 2;
                                break;
                            }
                            
                            else if ( decisao < 1 || decisao > 3 )
                            {
                                JOptionPane.showMessageDialog( null, "Tente novamente" );
                                break;
                            }
                            
                            personagem.aumentaPartHistoria();
                            menu++;
                            break;
                        }
                    }
                    
                    //DEFINIÇÃO DO HISTÓRICO
                    if ( menu == 3 )
                    {
                        while ( true )
                        {
                            try
                            {
                                s = JOptionPane.showInputDialog(historiaPrincipal.getHistoriaPrincipal(personagem.getPartHistoria()));
                                decisao = Integer.parseInt( s );
                                personagem.setHistorico(decisao);
                            }
                            catch ( NumberFormatException e )
                            {
                                JOptionPane.showMessageDialog( null, "Tente novamente" );
                                continue;
                            }

                            if ( decisao == 0 )
                            {
                                menu--;
                                personagem.diminuiPartHistoria();
                                break;
                            }
                            
                            else if ( 1 < decisao || decisao > 4 )
                            {
                                JOptionPane.showMessageDialog( null, "Tente novamente" );
                                break;
                            }
                            
                            personagem.aumentaPartHistoria();
                            menu++;
                            break;
                        }
                    }
                    
                    if ( menu == 4)
                    {
                        break;
                    }
                }
                
                //LOOP PARA INTERAÇÃO COM O JOGO E A HISTÓRIA
                while ( true )
                {
                    
                    //PARTES DA HISTÓRIA
                    if ( personagem.getSituacaoAtual() == 0 )
                    {
                        personagem.setNome(JOptionPane.showInputDialog( null, historiaPrincipal.getHistoriaPrincipal( personagem.getPartHistoria() ) ) );
                        personagem.aumentaPartHistoria();
                        
                        personagem.setSituacaoAtual(1);
                    }
                    
                    //MENU DO PERSONAGEM
                    else if ( personagem.getSituacaoAtual() == 1 )
                    {
                        
                        //LOOP PARA APRESENTAÇÃO DO MENU E ESCOLHA DA PRÓXIMA DECISÃO
                        while ( true)
                        {
                            try
                            {
                                s = JOptionPane.showInputDialog( null, ( "Nome: " + personagem.getNome() + "\nNivel: " + personagem.getNivel() + "\nOuro: " + personagem.getOuro() + "\nExperiência: " + personagem.getExpAtual() + " de " + personagem.getExpMaxima() + "\nForça: " + personagem.getForca() + " |   Agilidade: " + personagem.getAgilidade() + "    |   Inteligência: " + personagem.getInteligencia() + "\n\n0 - Sair do jogo |   1 - Salvar  |   2 - Explorar" ) );
                                decisao = Integer.parseInt( s );
                            }
                            catch ( NumberFormatException e )
                            {
                                JOptionPane.showMessageDialog( null, "Tente novamente" );
                                continue;
                            }
                            break;
                        }
                        
                        //CASO DECIDA SAIR DO JOGO
                        if ( decisao == 0 )
                            break;
                        
                        //CASO DECIDA SALVAR O JOGO
                        else if ( decisao == 1 )
                        {
                            ;
                            //salvar o jogo
                        }
                        
                        //CASO DECIDA EXPLORAR O JOGO
                        else if ( decisao == 2 )
                        {
                            try
                            {
                                s = JOptionPane.showInputDialog( null, ( "1 - Floresta  |   2 - Pântano\n3 - Deserto    |   4 - Montanha\n\n0 - Acampamento" ) );
                                decisao = Integer.parseInt( s );
                                personagem.setLocalAtual(decisao);
                            }
                            catch ( NumberFormatException e )
                            {
                                JOptionPane.showMessageDialog( null, "Tente novamente" );
                                continue;
                            }
                            break;
                        }
                    }
                    
                    //BATALHA
                    else if ( personagem.getSituacaoAtual() == 2 )
                    {
                        ;
                    }
                    
                    /*
                    * JOptionPane.showInputDialog(historiaPrincipal.getHistoriaPrincipal(personagem.getPartHistoria())); //texto + entrada
                    * JOptionPane.showMessageDialog(null, historiaPrincipal.getHistoriaPrincipal(personagem.getPartHistoria())); // texto + ok
                    * JOptionPane.showConfirmDialog(null, historiaPrincipal.getHistoriaPrincipal(personagem.getPartHistoria())); // texto + sim + não + cancelar
                    */
                    
                }
                break;
            }
            
            //CARREGAR PERSONAGEM
            else if ( decisao == 1 )
            {
                //Carregar o personagem
                break;
            }
            
            //SAIR DO JOGO
            else if ( decisao == 2 )
            {
                decisao = JOptionPane.showConfirmDialog(null, "Deseja mesmo sair?");
                if ( decisao == 0 )
                    break;
            }
        }
    }
}
