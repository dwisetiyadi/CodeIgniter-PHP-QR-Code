Markdown
========

Version 1 - Dec 2011
by dwi.setiyadi@gmail.com



Introduction
------------

This a library for CodeIgniter Framework to make QR Code from some string given, a porting code from http://phpqrcode.sourceforge.net/.



Installation and Requirements
-----------------------------

This library requires CodeIgniter Framework and GD2.


### How to use ###

On the fly generate

	$this->load->library('ciqrcode');
	
	$params['data'] = 'http://extradiskon.com';
	$params['level'] = 'H';
	$params['size'] = 10;
	
	header("Content-Type: image/png");
	$this->ciqrcode->generate($params);



Saved QR Code image example

	$this->load->library('ciqrcode');
	
	$params['data'] = 'http://extradiskon.com';
	$params['level'] = 'H';
	$params['size'] = 10;
	$params['savename'] = FCPATH.'tes.png';
	$this->ciqrcode->generate($params);
	
	echo '<img src="'.base_url().'tes.png" />';



Optional configuration

	$this->load->library('ciqrcode');
	
	$config['cacheable']	= true; //boolean, the default is true
	$config['cachedir']		= '';
	$config['errorlog']		= '';
	$config['quality']		= true; //boolean, the default is true
	$config['size']			= 1024;
	$this->ciqrcode->initialize($config);