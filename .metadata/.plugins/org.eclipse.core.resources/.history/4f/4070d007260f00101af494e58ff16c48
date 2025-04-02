package com.FetchingHibernate.hibernate;

import org.hibernate.Session;
import org.hibernate.SessionFactory;
import org.hibernate.Transaction;
import org.hibernate.boot.registry.BootstrapServiceRegistryBuilder;
import org.hibernate.boot.registry.StandardServiceRegistryBuilder;
import org.hibernate.cfg.Configuration;
import org.hibernate.service.ServiceRegistry;



/**
 * how to use embeddable object
 *
 */
public class App 
{
    public static void main( String[] args )
    {
    	fullName fname = new fullName();
    	fname.setFname("maari");
    	fname.setLname("muthu");
    	fname.setMname("appa name");
        num al =new num();
        al.setName(fname);// its a object
        al.setColor("black");
        al.setId(2);
        
        
//        al.setId(4);
//        al.setName("ru");
//        al.setColor("Black");
        
        Configuration con = new Configuration().configure().addAnnotatedClass(num.class);
        
        ServiceRegistry reg = new StandardServiceRegistryBuilder().applySettings(con.getProperties()).build();
        
        //buildsession is depricated so we using another method
        SessionFactory sf =  con.buildSessionFactory(reg);
        
        Session session = sf.openSession();
        
        Transaction tx = session.beginTransaction();
        
        session.save(al);
//        al = (num)session.get(num.class, 1);
        
        tx.commit();
        
        System.out.println(al);
    }
}
