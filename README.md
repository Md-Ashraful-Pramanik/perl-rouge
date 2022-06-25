# ROUGE Installation 
If you have sudo access please use the following command to install perl ROUGE, otherwise go to the [Section](#rouge-installation-without-sudo-access). I have taken some steps from this [Githib Gist](https://gist.github.com/Tbabm/65b5d8a3adb9845d55ce27143913e3b2).

### Check whether perl is installed or not
`perl --version`

### Installing CPAN
`sudo apt-get install cpanminus`

### Install XML::DOM
`sudo cpan XML::DOM`

### Download ROUGE-1.5.5
`git clone https://github.com/summanlp/evaluation`

### ROUGE 1.5.5 can be found in evaluation/ROUGE-RELEASE-1.5.5
`export ROUGE=/absolute/path/to/ROUGE-RELEASE-1.5.5`

### Optional: setting environment variable
`echo "export ROUGE=\"${ROUGE}\"" >> ~/.bashrc` <br>
`source ~/.bashrc`

### Modify the db file
`cd ${ROUGE}/data/WordNet-2.0-Exceptions/`<br>
`mv WordNet-2.0.exc.db WordNet-2.0.exc.db.bak`<br>
`./buildExeptionDB.pl . exc WordNet-2.0.exc.db`<br>

### Testing
`cd $ROUGE`<br>
`./runROUGE-test.pl`

# ROUGE Installation (Without sudo access)
First you need to install perl. There is no sudo commad so we can not install cpan directly. So, I have developed a way-around by using two file cpan and cpanm copy them to a directory and go to there. The rest of the proccess are described below-

### Check whether perl is installed or not
`perl --version`

### Installing App::Cpan to use cpan
`./cpanm App::Cpan`

When this installation is going it will give a message about the location where it stores the module note the location and add it with perl5lib
by using following command.<br>
`export PERL5LIB="path/to/the/directory:$PERL5LIB"`

### Installing DB file
`./cpanm DB_File`

### Install XML::DOM module
`./cpan XML::DOM`

Then the rest of the installation I have followed from a [Githib Gist](https://gist.github.com/Tbabm/65b5d8a3adb9845d55ce27143913e3b2)

### Download ROUGE-1.5.5
`git clone https://github.com/summanlp/evaluation`

### ROUGE 1.5.5 can be found in evaluation/ROUGE-RELEASE-1.5.5
`export ROUGE=/absolute/path/to/ROUGE-RELEASE-1.5.5`

### Optional: setting environment variable
`echo "export ROUGE=\"${ROUGE}\"" >> ~/.bashrc` <br>
`source ~/.bashrc`

### Modify the db file
`cd ${ROUGE}/data/WordNet-2.0-Exceptions/`<br>
`mv WordNet-2.0.exc.db WordNet-2.0.exc.db.bak`<br>
`./buildExeptionDB.pl . exc WordNet-2.0.exc.db`<br>

### Testing
`cd $ROUGE`<br>
`./runROUGE-test.pl`


