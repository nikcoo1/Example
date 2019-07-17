unit Unit1;

{$mode objfpc}{$H+}

interface

uses
  Classes, SysUtils, FileUtil, Forms, Controls, Graphics, Dialogs, StdCtrls, fphttpclient;

type

  { TForm1 }

  TForm1 = class(TForm)
    Button1: TButton;
    Memo1: TMemo;
    procedure Button1Click(Sender: TObject);
    function latestGitRelease(url: string): string;
  private
    { private declarations }
  public
    { public declarations }
  end;

var
  Form1: TForm1;

implementation

{$R *.lfm}

{ TForm1 }

procedure TForm1.Button1Click(Sender: TObject);
begin
  Memo1.Text:= latestGitRelease('http://192.168.99.18/query_test.php?q=1'); ;
end;

function TForm1.latestGitRelease(url: string): string;
//Returns string for latest release (error will return empty string)
//example
// latestGitRelease('https://api.github.com/repos/rordenlab/dcm2niix/releases/latest');
//will return
// "v1.0.20171204"
const
     key = '"tag_name":"';
var
  s, e: integer;
  cli: TFPHTTPClient;
begin
  result := '';
  cli := TFPHTTPClient.Create(nil);
  cli.AddHeader('User-Agent','Mozilla/5.0 (compatible; fpweb)');
  try
    try
      result := Cli.Get(url);
    except
      result := '';
    end;
  finally
    cli.free
  end;
end;





end.

