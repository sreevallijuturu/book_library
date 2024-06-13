class Library{
    String array[]=new String[100];
    String issuedBooks[]=new String[100];

    public void addBook(String book)
    {
        System.out.println(book+" book has been added to library");
        for(int i=1;i< array.length;i++)
        {
            if(array[i]==null)
            {
                array[i]=book;
                break;
            }
        }
    }
    public void showAvailableBooks()
    {
        System.out.println("the available books are:");
        for(int i=1;i< array.length;i++) {
            if (array[i] == null) {
                continue;
            } else {
                System.out.println("*" + array[i]);
            }
        }
    }
    public void returnBook(String book)
    {
        addBook(book);
    }
    public void issueBook(String book)
    {
        for(int i=1;i< array.length;i++)
        {
            if(array[i].equals(book))
            {
                for(int j=1;j< issuedBooks.length;j++)
                {
                    if(issuedBooks[j]==null)
                    {
                        issuedBooks[i]=book;
                        break;
                    }
                }
                array[i]=null;
                break;
            }
        }
    }
    public void showIssuedBooks()
    {
        System.out.println("The issued books are");
        for(String elements:issuedBooks)
        {
            if(elements!=null)
            System.out.println("*"+elements);
        }
    }


}
public class making_a_book_library{
    public static void main(String[] args) {
      Library obj=new Library();
      obj.addBook("oop with java");
      obj.addBook("programming with c");
     //  obj.showAvailableBooks();
      obj.returnBook("code with harry");
      obj.showAvailableBooks();
      obj.issueBook("code with harry");
      obj.issueBook("oop with java");
      obj.showAvailableBooks();
      obj.showIssuedBooks();
    }
}